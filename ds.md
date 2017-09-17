project_name
type_name
sharp
dwg_no
item_code
drawing_detail


public int DT_Dwg_ID { get; set; }
        public string DT_Revise { get; set; }
        public string DT_ProjectName { get; set; }
        public string DT_TypeName { get; set; }
        public int DT_Sharp { get; set; } //show
        public string DT_Dwg_No { get; set; }
        public string DT_Dwg_Code { get; set; }
        public DateTime? DT_Plan_Date { get; set; } //show
        public DateTime? DT_Actual_Date { get; set; } //show
        public string DT_Drawing_Details { get; set; }
        public int DT_QTY { get; set; }
        public int DT_TotalQTY { get; set; }
        public string DT_CREATE_BY { get; set; } //show
        public DateTime? DT_CREATE_DATE { get; set; } //show
        public string DT_UPDATE_BY { get; set; } //show
        public DateTime? DT_UPDATE_DATE { get; set; } //show
        public string DT_Remark { get; set; } //show

      string project_name,
      string type_name  ,
      int? sharp_name,
      string dwg_no,
      string item_code ,
      string dwg_detail



      <p>
      <b><u> Project Name </u></b>: AkasakaI #1
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        <b> <u>Type </u></b>: Beam
        &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;
         <b><u>Process Name</u></b>: Shop Plan <br>
        <b><u>From-To</u></b>: Japan --&gt; OOOH
        &nbsp;&nbsp;&nbsp;
        &nbsp;&nbsp;&nbsp;
        &nbsp;&nbsp;&nbsp;
          </p>

          Date Plan
          Date Actual
          User Actual

          vertical-align: middle;
    font-size: 25px




    var c = from f in Tb_report_dwg_centers
                     join pj in Tb_projects on f.Project_ID equals pj.Project_ID
                     join ty in Tb_types on f.Type_ID equals ty.Type_ID
                     join pc in Tb_processes on f.Process_ID equals pc.Process_ID
                    /* join set_sch in Tb_set_schedules on f.Project_ID equals set_sch.Project_ID
                     join set_pc in Tb_set_schedules on f.Process_ID equals set_pc.Process_ID*/
                     join fo in Tb_froms on f.From_ID equals fo.From_ID
                     join to in Tb_froms on f.To_ID equals to.From_ID
                     where (pj.Project_Name == "AkasakaI" && pc.Process_Name == "Shop Plan" && ty.Type_Name == "Beam" && f.Dwg_No == "D00001" && f.Shape == 1 && f.Dwg_Code == "C00001")
					 select f;

					 c.Dump();


           O000059
           leekl123
O001429
1612
