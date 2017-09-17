IF A = B || C = D || E = F
     T   ||   T   ||   T

     Project_Name
     Type
     Sharp
     DWG_Detail_Name
     DWG_No
     ITEM_Code
     Adjust_Date
     Adjust_Total_QTY
     Adjust_Remark

     Shinhibiya
     Beam
     9
     Joint
     D00001
     C00001
     12-Jul-17
     2
     Adjust Info List

----------------------------------------------------------
 ส ง ส
Actaul Report Center

Project_Name
Type
Sharp
Process_Code
DWG_No
ITEM_Code
Actaul_Date



--TB
/*
-- User Table
SELECT * FROM Login
SELECT * FROM Role
---------------------
-- Main Data Table
--- Infomation
SELECT * FROM tb_from --> Customer Info
SELECT * FROM tb_process --> Process Data
SELECT * FROM tb_project --> Project
SELECT * FROM tb_type --> Type
SELECT * FROM tb_shape
SELECT * FROM tb_detail_dwg_list --> DWG list Details
--- Main
SELECT * FROM tb_set_schedule  --> Schedule and Process
SELECT * FROM tb_sum_schedule  --> Main Schedule
SELECT * FROM tb_report_dwg_center --> Main Center
SELECT * FROM tb_dwg_list --> Main DWG List
-----------------------------------------------------
SELECT * FROM tb_edit
SELECT * FROM tb_edit_dc
-----------------------------------------------------
-- Table Temp Load
--> Schedule Process
SELECT * FROM UploadTempScheduleProcess
-- Temp Schedule
SELECT * FROM UploadTempSchedule
SELECT * FROM EditTempSchedule
SELECT * FROM ActualTempSchedule
-- Temp Center
SELECT * FROM UploadTempInfoReportCenter
SELECT * FROM EditTempInfoReportCenter
SELECT * FROM ActualTempInfoReportCenter
-- Temp List
SELECT * FROM UploadTempReportInfoList
SELECT * FROM EditTempReportInfoList
SELECT * FROM ActualTempReportInfoList
*/

/*
-- Insert Schedule Process Temp to Real***
SELECT * FROM tb_project --> Project
SELECT * FROM tb_process --> Process Data
SELECT * FROM tb_from --> Customer Info
SELECT * FROM tb_set_schedule  --> Schedule and Process
SELECT * FROM UploadTempScheduleProcess
INSERT INTO
-- find Project_name --> SELECT * FROM tb_project --> Project
-- Project_Name

-- Insert Schedule Temp To Real
*/



https://www.asp.net/mvc/overview/getting-started/introduction/adding-a-controller

https://www.youtube.com/watch?v=loSRtJgr-fs

https://www.asp.net/mvc/mvc5

https://www.asp.net/mvc/overview/getting-started/introduction/getting-started

http://www.itgenius.co.th/Basic-ASP.net-4.0.html

http://www.thaicreate.com/community/itgenius-training.html

https://www.codeproject.com/Articles/866143/Learn-MVC-Project-in-days-Day

https://www.youtube.com/watch?v=z9sjZWDtzOw

http://forwardtoyou.blogspot.com/2013/06/advane-aspnet-mvc-framework.html
