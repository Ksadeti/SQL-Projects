-- Heading for Employee Data

-- Data Types, Querying Filtering, and Sorting.

SELECT Gender, Age, `Work Type`, `Cost Centre`, PayType, TernureMonths, `Current Salary`, `Current Employee Rating`, `Current Salary`/12 as `Salary per Month`, monthname(TernureMonths) as Lastest_Month
FROM me.hr_data
WHERE `Work Type` = 'Full Time' OR `Work Type` = 'Part Time'
AND Gender like'%M%';

-- Aggregation and Data Manipulation

SELECT `Cost Centre`, SUM(`Current Salary`) AS TotalSalary, avg(`Current Salary`) as AverageSalary, avg(Age) as AverageAge, count(`Current Employee Rating`) as TotalRatings, max(HireDate)
FROM me.hr_data
GROUP BY `Cost Centre`
ORDER BY TotalSalary desc; 

-- Update the Current Salary 
SELECT * FROM me.hr_data;

UPDATE me.hr_data
SET `Current Salary` = '46000'
WHERE Gender = Female AND Age = '64' AND EmployeeID = '23292';

-- Display the data after the update
SELECT * FROM me.hr_data;


-- Display the data before the delete
SELECT * FROM me.hr_data;

-- Delete the record
DELETE FROM me.hr_data
WHERE EmployeeID = '22416';

-- Display the data after the delete
SELECT * FROM me.hr_data;



-- Stored Procedure
GetEmployeeDataDELIMITER //

CREATE PROCEDURE GetEmployeeData()
BEGIN
	SELECT *, 
		CASE
		    WHEN Age <= 30 THEN 'Young'
            WHEN Age < 45 THEN 'Adult'
            ELSE 'Old'
	    END AS Age_Group
	FROM me.hr_data as hr
	WHERE Gender IN ('Female','Male') AND Age BETWEEN 15 AND 66
	ORDER BY EthnicGroup ASC
	limit 10;
END //

DELIMITER ;
