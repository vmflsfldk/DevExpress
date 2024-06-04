# DevExpress


# Grid에서 인접한 두 셀의 값이 같은 경우, 셀 Merge

1. 속성 - Gridview - AllCellMerge - True 로 변경

'''Csharp
GridView gridView = this.gridControl1.MainView as GridView;
   gridView.OptionsView.AllowCellMerge = true;
'''
   둘 중 하나 선택 하여 사용
# 특정 셀 색상 변경

```csharp
using System;
using System.Drawing;
using DevExpress.XtraGrid.Views.Grid;

namespace YourNamespace
{
    public partial class YourForm : Form
    {
        public YourForm()
        {
            InitializeComponent();
            gridControl1.DataSource = GetDataSource();
            gridView1.RowCellStyle += gridView1_RowCellStyle;
        }

        private void gridView1_RowCellStyle(object sender, RowCellStyleEventArgs e)
        {
            if (e.Column.FieldName == "YourColumnName")
            {
                var cellValue = gridView1.GetRowCellValue(e.RowHandle, e.Column);
                if (cellValue != null && cellValue.ToString() == "특정값")
                {
                    e.Appearance.BackColor = Color.Yellow; // 배경색 변경
                    e.Appearance.ForeColor = Color.Red; // 글자색 변경
                }
            }
        }

        private object GetDataSource()
        {
            // 데이터 소스를 반환하는 메서드를 구현합니다.
            return null;
        }
    }
}
