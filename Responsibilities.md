
/////////////AppointmentDesk////////////
1. IsWithinBusinessHours
determines if appoinment within clinic's busniss hours

2. FindNextSlot
   TryBook
   
   finds next avilable appointment and books appointment

3. ToIcs
 Generates ICS calendar representation for appointment

4.SmsReminder
Generates SMS reminder for appointment

the problem that appoinmentdesk is doing many tasks in one class,handels business hours and appointments
gemerate calender and sent sms reminders ,if one of these change we should change all class even though the responsibilities are not related.


/////////////CheckoutBasket////////////

1. basket
   - Add items to the basket.
   - Apply coupons and calculate discounts.
   - Calculate the subtotal and grand total.

  2.Gift
   - Enable gift wrapping.
   - Generate the gift message.
  
    3.Payment Authorization
   - Generates a payment authorization
   - 
the problem that CheckoutBasket is doing too many different tasks. It is responsible for managing the basket,
calculating prices and discounts, handling gifts, and authorizing payments 
this means that change in one responsibility can affect the same class, even if the other responsibilities do not need to change.

/////////////CourseEnrollmentDesk////////////

1. Registration
   - Register -> is responsible for registering students in the course or adding them to the waitlist.

2. Waitlist
   - WaitlistPosition ->checks the student's position in the waitlist.
   - PromoteFromWaitlist ->moves students from the waitlist when seats become available.

3. Tuition Invoice
   - TuitionInvoiceLine ->generates the tuition invoice line and calculates the VAT and total amount.

4. Welcome Packet
   - WelcomePacketMarkdown-> generates the welcome packet in Markdown format.

The problem is that CourseEnrollmentDesk handles different responsibilities in the same class. 
It manages student registration and the waitlist, but it also generates welcome packets and tuition invoices.
If one of these responsibilities changes, we may need to modify the same class even when the change is not related to the other responsibilities.
This makes the class harder to maintain.


/////////////GradeBook////////////

1.Score 
   - Record -> responsible for recording students' scores.
   - Average-> responsible for calculating the student's average score.

2. rules
   - Letter is responsible for determining the letter grade based on the student's average.
   

3.rules
- MeetsHonorRoll->  responsible for checking whether a student meets the honor roll requirements.
- 
4.CSV Export
   - ExportCsv->  responsible for exporting the grade information in CSV format.
   - TranscriptPlain -> responsible for generating a plain-text transcript for a student.


The problem is that GradeBook handles several different responsibilities in the same class
It records and calculates grades, applies academic rules, generates transcripts, and exports data to CSV 
If one of these responsibilities changes, we may need to modify the same class even when the other responsibilities do not need to change
This makes the class harder to maintain.



/////////////KitchenTicket////////////

1.Order Management
   - AddItem -> responsible for adding items and their ingredients and preparation time.

2. Allergen Detection
   - DetectAllergens-> responsible for detecting allergens from the ingredients.

3. Kitchen Operations
   - EstimatedReadyMinutes-> calculates the estimated preparation time.
   - ExpoLaneHint-> determines the appropriate kitchen lane based on allergens and preparation time.

4. Thermal Ticket Render
 - RenderThermalTicket-> is responsible for generating the formatted thermal printer ticket.

The problem is that KitchenTicket handles different responsibilities in the same class 
It manages order items, detects allergens, calculates kitchen preparation time, and formats the thermal ticket
If one of these responsibilities changes, we may need to modify the same class even when the change is unrelated to the other responsibilities
This makes the class harder to maintain

/////////////LoanDesk////////////

1.Loan Risk and Eligibe
   -RiskScore-> calculates the applicant's risk score.
   -IsEligible-> determines whether the applicant is eligible for the loan.

2.Required Documents
   -RequiredDocuments-> determines which documents are required for the application.

3. Decision Letter
   - DecisionLetter-> generates the decision letter for the applicant.

4. Underwriter CSV Export
   - UnderwriterCsvRow-> generates a CSV row containing the application information and decision data.

The problem is that LoanDesk handles different responsibilities in the same class. It calculates loan risk and eligibility,
determines the required documents, generates decision letters,
and creates CSV data for underwriters. If one of these responsibilities changes, 
we may need to modify the same class even when the change is unrelated to the other responsibilities, This makes the class harder to maintain.

/////////////SubscriptionBilling////////////

1. Prorate
   - Prorate-> calculates the subscription amount based on the active period.

2. Invoice Number
   - NextInvoiceNumber-> generates the next invoice number.

3. Failed Payment 
   - RegisterFailedPayment-> records failed payments.

4. Dunning Email Generation
   - DunningEmail->generates email for failed payments.

5. Ledger Export
   - LedgerJournalLine-> generates the accounting journal line.

The problem is that SubscriptionBilling handles several different responsibilities in the same class. It calculates subscription prices, 
generates invoice numbers, tracks failed payments, creates dunning emails, and generates accounting data. 
These responsibilities can change for different reasons, so keeping them together makes the class harder to maintain.

/////////////SupportTicket////////////

1. Customer Message
   - AppendCustomerMessage ->adds a customer message to the ticket.

2. Priority Calculation
   - `RecalculatePriorityFromText->calculates the ticket priority based on its text.

3. SLA Management
   - slaDeadline-> calculates the SLA deadline.
   - IsBreached-> checks whether the SLA has been breached.

4. Public Reply
   - DraftPublicReply-> generates a public reply to the customer.

5. Internal Escalation 
   - InternalEscalationBlurb->generates an internal escalation message.

The problem is that SupportTicket handles several different responsibilities in the same class. It manages customer messages, calculates priority,
handles SLA rules, generates public replies, and creates internal escalation messages. These responsibilities can change for different reasons, 
so keeping them together makes the class harder to maintain.

/////////////WardBoard////////////

1.Manage Bed and Patient 
   - AssignBed-> assigns a patient to a bed and stores their information.

2. Calculate Acuity Score Calculation
   - ScoreAcuity ->calculates the patient's acuity score based on heart rate and oxygen level.

3. Pager Alert
   - AssignBed-> adds a pager alert when the acuity score reaches the required threshold.
   - DrainPagerLog-> returns and clears the pager log.

4. Nurse Handoff Note
   - BuildHandoffNote->generates a handoff note containing the bed, patient, acuity, and status.

5. Census CSV Export
   - ExportCensusCsv-> generates the ward census data as a CSV file.

The problem is that WardBoard handles several different responsibilities in the same class. It manages beds and patients,
calculates acuity scores, handles pager alerts, generates nurse handoff notes, and exports census data to CSV.
These responsibilities can change for different reasons, so keeping them together makes the class harder to maintain.

/////////////WarehousePickList////////////

1. Warehouse Need
   - AddNeed-> adds the required product information to the pick list.

2. Stock Allocation
   - Allocate-> calculates how much of each product can be allocated based on the needed and available quantities.

3. Walking Order
   - WalkingOrder-> determines the order in which the picker should visit aisles and bins.

4. Picker
   - PickerScript-> generates instructions for the picker and shows any shortages.

5. WMS XML Integration
   - WmsXmlBatch-> generates an XML batch for the warehouse management system.

The problem is that WarehousePickList handles several different responsibilities in the same class. It manages warehouse needs,
allocates stock, determines the walking order, generates picker instructions, and creates XML data for the WMS. 
These responsibilities can change for different reasons, so keeping them together makes the class harder to maintain.