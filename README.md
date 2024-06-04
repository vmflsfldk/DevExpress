# DevExpress


# Grid에서 인접한 두 셀의 값이 같은 경우, 셀 Merge

1. 속성 - Gridview - AllCellMerge - True 로 변경

'''C#
2. GridView gridView = this.gridControl1.MainView as GridView;
   gridView.OptionsView.AllowCellMerge = true;
'''
   둘 중 하나 선택 하여 사용
# 특정 셀 색상 변경
