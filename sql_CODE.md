/****** Script for SelectTopNRows command from SSMS  ******/
SELECT *
  FROM [MCSDRAWING].[dbo].[UploadTempScheduleProcess]

  /****** Script for SelectTopNRows command from SSMS  ******/
SELECT *
 FROM [MCSDRAWING].[dbo].[tb_set_schedule]

 commit

 DELETE FROM [MCSDRAWING].[dbo].[UploadTempScheduleProcess]

 DELETE FROM [MCSDRAWING].[dbo].[tb_set_schedule]
 WHERE Project_ID = 93

 EXEC [M_COMP_SP_SET_INS_SCHEDULE_PROCESS] 1,'14,15,16'


DECLARE @Str VARCHAR(50)
DECLARE @INTF INT

SET @Str = '1,2,3,4,5,6,7,8'

SET @Str = replace(@Str, "'", "")
SELECT  '' as strb

set path = replace(path, 'oldstring', 'newstring')

-----------------------------------------------------

SELECT * FROM Login -- 7.
SELECT * FROM Role -- 8.
SELECT * FROM tb_edit -- 11.
SELECT * FROM tb_edit_dc -- 10.

Main
SELECT * FROM tb_set_schedule -- 16.
SELECT * FROM tb_sum_schedule -- 18.
SELECT * FROM tb_report_dwg_center -- 15.
SELECT * FROM tb_dwg_list -- 10.


Data_Set
SELECT * FROM tb_project -- 14. Project Main
SELECT * FROM tb_process -- 13.
SELECT * FROM tb_from -- 12. set ค่าเข้าดึงจาก customer
SELECT * FROM tb_detail_dwg_list -- 9.
SELECT * FROM tb_type -- 19.
----
SELECT * FROM tb_shape -- 17.

TEMP_Data

SELECT * FROM UploadTempSchedule -- 23. ORDER BY PROJECT_NAME,PROCESS_CODE,Sharp
SELECT * FROM UploadTempInfoReportCenter -- 20.
SELECT * FROM UploadTempReportInfoList -- 21.
SELECT * FROM UploadTempScheduleProcess -- 22.
--------------
Actual -- Update Data

SELECT * FROM ActualTempInfoReportCenter -- 1.
SELECT * FROM ActualTempReportInfoList -- 2.
SELECT * FROM ActualTempSchedule -- 3.

Adjust

SELECT * FROM EditTempInfoReportCenter -- 4.
SELECT * FROM EditTempReportInfoList -- 5.
SELECT * FROM EditTempSchedule -- 6.


DECLARE @SETTYPE INT
DECLARE @SET_DATA VARCHAR(MAX)
SET @SETTYPE = 1
SET @SET_DATA = '108,109,110'
EXEC [M_TODO_SP_SET_INS_SCHEDULE_TEMP] @SETTYPE,@SET_DATA
PRINT 'DONE'


----------------------------------
/*
TEST SCHEDULE
SELECT * FROM tb_set_schedule -- 16.

---DELETE FROM tb_sum_schedule WHERE Project_ID = 93
SELECT * FROM tb_sum_schedule -- 18.
SELECT * FROM UploadTempSchedule -- 23. ORDER BY PROJECT_NAME,PROCESS_CODE,Sharp
EXEC [SP_SET_INS_SCHEDULE_TEMP] 1,'1,2,3,4,5,6'
*/
--------------------------------------------
/*
INPUT

- Run_id => INT
- status => VARCHAR(10) => create
- Revision =>

Project_Name => VARCHAR(100)
Type	=> VARCHARR(50)
Sharp	=> INT
Process_Code => VARCHAR(10)
DWG_No	=> VARCHAR(20)
ITEM_Code	=> VARCHAR(20)
Pcs	=> INT
Plan_Date => DATETIME
User_Plan => VVARCHAR()
Remark

CREATE_BY
CREATE_DATE
isActive

SELECT * FROM UploadTempInfoReportCenter -- 20.

INSERT TO
SELECT * FROM tb_report_dwg_center -- 15

Report_ID --> running number
Porject_ID => INT
Type_ID => INT
Dwg_No => VARCHAR(20)
Dwg_Code => VARCHAR(20)
Plandate => DATETIME
Process_Code => INT
Shape => INT
From_ID => INT
To_ID => INT



*/


------------------------------------------------------------

SELECT * FROM tb_project -- 14. Project Main
SELECT * FROM tb_process -- 13.


-------------------------------


SELECT * FROM Login -- 7.
SELECT * FROM Role -- 8.
SELECT * FROM tb_edit -- 11.
SELECT * FROM tb_edit_dc -- 10.

Main
SELECT * FROM tb_set_schedule -- 16.
SELECT * FROM tb_sum_schedule -- 18.
SELECT * FROM tb_report_dwg_center -- 15.
SELECT * FROM tb_dwg_list -- 10.


Data_Set
SELECT * FROM tb_project -- 14. Project Main
SELECT * FROM tb_process -- 13.
SELECT * FROM tb_from -- 12. set ค่าเข้าดึงจาก customer
SELECT * FROM tb_detail_dwg_list -- 9.
SELECT * FROM tb_type -- 19.
----
SELECT * FROM tb_shape -- 17.

TEMP_Data

SELECT * FROM UploadTempSchedule -- 23. ORDER BY PROJECT_NAME,PROCESS_CODE,Sharp
SELECT * FROM UploadTempInfoReportCenter -- 20.
SELECT * FROM UploadTempReportInfoList -- 21.
SELECT * FROM UploadTempScheduleProcess -- 22.
--------------
Actual -- Update Data

SELECT * FROM ActualTempInfoReportCenter -- 1.
SELECT * FROM ActualTempReportInfoList -- 2.
SELECT * FROM ActualTempSchedule -- 3.

Adjust

SELECT * FROM EditTempInfoReportCenter -- 4.
SELECT * FROM EditTempReportInfoList -- 5.
SELECT * FROM EditTempSchedule -- 6.


DECLARE @SETTYPE INT
DECLARE @SET_DATA VARCHAR(MAX)
SET @SETTYPE = 1
SET @SET_DATA = '108,109,110'
EXEC [M_TODO_SP_SET_INS_SCHEDULE_TEMP] @SETTYPE,@SET_DATA
PRINT 'DONE'


----------------------------------
/*
TEST SCHEDULE
SELECT * FROM tb_set_schedule -- 16.

---DELETE FROM tb_sum_schedule WHERE Project_ID = 93
SELECT * FROM tb_sum_schedule -- 18.
SELECT * FROM UploadTempSchedule -- 23. ORDER BY PROJECT_NAME,PROCESS_CODE,Sharp
EXEC [SP_SET_INS_SCHEDULE_TEMP] 1,'1,2,3,4,5,6'
*/
--------------------------------------------
/*
INPUT

- Run_id => INT
- status => VARCHAR(10) => create
- Revision =>

Project_Name => VARCHAR(100)
Type	=> VARCHARR(50)
Sharp	=> INT
Process_Code => VARCHAR(10)
DWG_No	=> VARCHAR(20)
ITEM_Code	=> VARCHAR(20)
Pcs	=> INT
Plan_Date => DATETIME
User_Plan => VVARCHAR()
Remark

CREATE_BY
CREATE_DATE
isActive

SELECT * FROM UploadTempInfoReportCenter -- 20.

INSERT TO
SELECT * FROM tb_report_dwg_center -- 15

SELECT * FROM tb_report_dwg_center
WHERE
Project_ID = @Project_ID
and Process_ID = @Process_ID
and Shape_Name = @I_Sharp
and Type_ID = @Type_ID

and isActive = 1


Report_ID --> running number
Project_ID => INT
Type_ID => INT
Dwg_No => VARCHAR(20)
Dwg_Code => VARCHAR(20)
Plandate => DATETIME
Process_Code => INT
Shape => INT

From_ID => INT
To_ID => INT



*/
SELECT * FROM tb_sum_schedule WHERE Project_ID = 93 and Process_ID = 1 and Shape_Name = 9 and Type_ID = 1 and isActive = 1

------------------------------------------------------------

SELECT * FROM tb_project -- 14. Project Main
SELECT * FROM tb_process -- 13.
