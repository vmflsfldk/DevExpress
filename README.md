# DevExpress


# Grid에서 인접한 두 셀의 값이 같은 경우, 셀 Merge

1. 속성 - Gridview - AllCellMerge - True 로 변경
2.
```csharp
GridView gridView = this.gridControl1.MainView as GridView;
gridView.OptionsView.AllowCellMerge = true;
```
둘 중 하나 사용하여 설정

# 특정 셀 색상 변경

GridView에 RowStyle 이벤트 추가

```csharp
(this.gridControl1.MainView as GridView).RowStyle += gridView1_RowStyle;
```

```csharp
private void gridView1_RowStyle(object sender, RowStyleEventArgs e)
{
    GridView View = sender as GridView;
    if (e.RowHandle >= 0)
    {
        // 컬럼 값이 QtySum인 컬럼의 Cell 값을 찾아옴
        string product = View.GetRowCellDisplayText(e.RowHandle, View.Columns["QtySum"]);
        // QtySum이 90000 이상 인 값 셀 색 변경
        if (QtySum >= 90000)
        {
            // Row의 배경색을 변경합니다.
            e.Appearance.BackColor = Color.skyblue;
        }
    }
}
```
