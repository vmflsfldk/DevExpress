# DevExpress


# Grid에서 인접한 두 셀의 값이 같은 경우, 셀 Merge

1. 속성 - Gridview - AllCellMerge - True 로 변경

```csharp
GridView gridView = this.gridControl1.MainView as GridView;
gridView.OptionsView.AllowCellMerge = true;


