Create Project
-
Create Process
Create Target
Mapping Project and Process -> Schedule Process

Report Schedule
Upload Drawing Schedule By Sharp
- Project_ID
- Project_Name
- Process_ID
- Process_Name
- Process_From_ID
- Process_From_Name
- Process_To_ID
- Process_To_Name
- Sharp
- Type_ID
- Type_Name
- Remark
- Update_Date
- Update_By

--Excel
- Project_ID
- Project_Name
- Type_ID
- Type_Name
- Sharp
- Process_Code
- Plan
- Remark

------------------
Create

MCSAPP

1 Project have any Schedule
name schedule

- TB -> Main_Project

mp_id -> int  :id project
ct_id -> int  : ?
mp_name -> nvarchar(64) : real name :: Tamachi
mp_sname -> nvarchar(3) : shot name
mp_date_close -> datetime : date close project

-----------------------------------------------
DWG

- TB -> Product_TYPE

DWG_pt_id -> int : not null
DWG_pt_name -> nvarchar(32)
DWG_pt_user_open -> nvarchar(7)
DWG_pt_date_open -> datetime
DWG_pt_user_close -> nvarchar(7)
DWG_pt_date_close -> datetime
DWG_pt_state -> smallint
DWG_pt_ts -> timestamp
DWG_pt_ItemType -> nvarchar(5)
DWG_pt_mainType -> int

-----------------------------------------

Project Main set

- TB -> Main_Project_Data

Project_ID -> int
Is_Active -> int
Project_Name -> varchar(100)
Project_ShortName -> varchar(100)
Project_Detail -> varchar(255)

 Upload Drawing Schedule

- TB_UPLOAD_DWG_SCHEDULE_Log

Schedule_UP_ID -> int
PJ_ID -> int
Schedule_ID -> int
Schedule_TYPE -> varchar
Schedule_SHARP -> int
Schedule_PROCESS_CODE -> varchar
Schedule_PROCESS_NAME -> varchar
Schedule_FROM -> varchar
Schedule_TO -> varchar
Schedule_PLAN -> datetime
Schedule_REMARK -> nvarchar(MAX)
Schedule_REV -> int
CREATE_BY -> varchar
CREATE_DATE -> datetime
UPDATE_BY -> varchar
UPDATE_DATE -> datetime


Project_Name -> Project_ID
Type -> Type_ID
Sharp -> Sharp
Process_Code -> Process_ID
Plan -> ""
Remark -> ""

SP_LOAD_DWG_SHEDULE('Akasaka','Beam',9,'P01','DATETIME','REMARK')
