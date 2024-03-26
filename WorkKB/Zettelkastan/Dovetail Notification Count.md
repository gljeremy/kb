[[Dovetail]] 

Getting Notification Count - GetEmployeeCases

1. Change approach for retrieving the Notification Count 
	
	Add method for Getting Notification Count
	High request count observed on: /api/v1/employees/222558/cases?page=1&sortBy=lastModified&sortOrder=desc&per_page=50
	
	Which retrieves 50 cases that have to be hydrated and sorted
	
	Recommend replace with:
	/api/v1/employees/244002/cases?page=1&per_page=1&hasUpdates=true&availableInPortal=True
	(See: https://latest.dovetailnow.com/api/doc#Cases@Employee)
	
	Which retrieves 1 or 0 cases and could be retrieved.
	
	Then look at the header values
	* X-Total-Count: total cases that match the filters, across all pages
	* X-Updates-Count: total unread cases. It does honor the availableInPortal filter.
	
2. Cache responses from the Notification Count for 1-2 minutes. Expire when MarkCaseAsReadAsync
3. Reduce cases page size from 50 to 10
4. GetEmployeeCasesAsync -- Always **availableInPortal** param - See: https://latest.dovetailnow.com/api/doc#Cases@Employee
5. Notify Dovetail next time a new client is onboarded or usage spike is expected.

