
-- Table: Organizer
CREATE TABLE Organizer (
    OrganizerID INT PRIMARY KEY,
    OrganizerName VARCHAR(100),
    ContactInfo VARCHAR(100),
    Email VARCHAR(100)
);

-- Table: Event
CREATE TABLE Event (
    EventID INT PRIMARY KEY,
    EventName VARCHAR(100),
    EventType VARCHAR(50),
    EventDate DATE,
    StartTime TIME,
    EndTime TIME,
    Location VARCHAR(100),
    Description TEXT,
    OrganizerID INT,
    Capacity INT,
    FOREIGN KEY (OrganizerID) REFERENCES Organizer(OrganizerID)
);

-- Table: Participant
CREATE TABLE Participant (
    ParticipantID INT PRIMARY KEY,
    ParticipantName VARCHAR(100),
    ContactInfo VARCHAR(100),
    Email VARCHAR(100)
);

-- Table: Registration
CREATE TABLE Registration (
    RegistrationID INT PRIMARY KEY,
    ParticipantID INT,
    EventID INT,
    RegistrationDate DATE,
    Status VARCHAR(50),
    PaymentStatus VARCHAR(50),
    FOREIGN KEY (ParticipantID) REFERENCES Participant(ParticipantID),
    FOREIGN KEY (EventID) REFERENCES Event(EventID)
);

-- Table: Staff
CREATE TABLE Staff (
    StaffID INT PRIMARY KEY,
    StaffName VARCHAR(100),
    ContactInfo VARCHAR(100),
    Email VARCHAR(100),
    Role VARCHAR(50)
);

-- Table: Performance (Example for specific event types like concerts)
CREATE TABLE Performance (
    PerformanceID INT PRIMARY KEY,
    EventID INT,
    ArtistName VARCHAR(100),
    StartTime TIME,
    EndTime TIME,
    FOREIGN KEY (EventID) REFERENCES Event(EventID)
);

-- Example of inserting data into Organizer table
INSERT INTO Organizer (OrganizerID, OrganizerName, ContactInfo, Email)
VALUES (1, 'Example Festival Organizer', '123-456-7890', 'organizer@example.com');

-- Example of inserting data into Event table
INSERT INTO Event (EventID, EventName, EventType, EventDate, StartTime, EndTime, Location, Description, OrganizerID, Capacity)
VALUES (1, 'Opening Ceremony', 'Ceremony', '2024-08-01', '18:00:00', '20:00:00', 'Main Stage', 'Opening event of the festival', 1, 500);

-- Example of inserting data into Participant table
INSERT INTO Participant (ParticipantID, ParticipantName, ContactInfo, Email)
VALUES (1, 'John Doe', '987-654-3210', 'john.doe@example.com');

-- Example of inserting data into Registration table
INSERT INTO Registration (RegistrationID, ParticipantID, EventID, RegistrationDate, Status, PaymentStatus)
VALUES (1, 1, 1, '2024-07-15', 'Confirmed', 'Paid');

-- Example of inserting data into Staff table
INSERT INTO Staff (StaffID, StaffName, ContactInfo, Email, Role)
VALUES (1, 'Jane Smith', '555-123-4567', 'jane.smith@example.com', 'Event Coordinator');

-- Example of inserting data into Performance table
INSERT INTO Performance (PerformanceID, EventID, ArtistName, StartTime, EndTime)
VALUES (1, 1, 'Acoustic Band', '19:00:00', '20:30:00');
<!---
CHUMMI2003/CHUMMI2003 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
