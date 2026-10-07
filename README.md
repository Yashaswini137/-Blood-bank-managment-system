CREATE TABLE Donor ( 
    DonorID INT PRIMARY KEY, 
    Name VARCHAR(100), 
    Age INT CHECK (Age >= 18), 
    Gender VARCHAR(10), 
    BloodGroup VARCHAR(5), 
    Contact VARCHAR(15) 
);  
CREATE TABLE Hospital ( 
    HospitalID INT PRIMARY KEY, 
    Name VARCHAR(100), 
    Location VARCHAR(100), 
    Contact VARCHAR(15) 
); 
 
CREATE TABLE BloodInventory ( 
    InventoryID INT PRIMARY KEY, 
    BloodGroup VARCHAR(5), 
    Quantity INT DEFAULT 0, 
    LastUpdated DATE 
); 
CREATE TABLE Request ( 
    RequestID INT PRIMARY KEY, 
    HospitalID INT, 
    BloodGroup VARCHAR(5), 
    Quantity INT, 
    RequestDate DATE, 
    Status VARCHAR(20), 
    FOREIGN KEY (HospitalID) REFERENCES Hospital(HospitalID); 
