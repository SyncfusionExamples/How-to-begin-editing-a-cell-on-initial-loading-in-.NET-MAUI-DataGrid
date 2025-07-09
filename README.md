# How to begin editing a cell on initial loading in .NET MAUI DataGrid?

This article demonstrates how to begin editing a cell on initial loading in [.NET MAUI DataGrid](https://www.syncfusion.com/maui-controls/maui-datagrid)(SfDataGrid).

To begin editing a specific cell when the .NET MAUI SfDataGrid is initially loaded, you can use the [DataGridLoaded](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.DataGrid.SfDataGrid.html#Syncfusion_Maui_DataGrid_SfDataGrid_DataGridLoaded) event. This event is triggered once the DataGrid and its components are fully initialized and rendered. By invoking the [BeginEdit](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.DataGrid.SfDataGrid.html#Syncfusion_Maui_DataGrid_SfDataGrid_BeginEdit_System_Int32_System_Int32_) method within this event, you can programmatically start editing a particular cell.

## Xaml

``` xml
<ContentPage.Content>

     <syncfusion:SfDataGrid 
             x:Name="dataGrid"
             AllowEditing="True"
             SelectionUnit="Cell"
             SelectionMode="Single"
             ItemsSource="{Binding OrderInfoCollection}">
     </syncfusion:SfDataGrid>
     
 </ContentPage.Content>
```

## Xaml.cs

```c#
  public partial class MainPage : ContentPage
  {
      public MainPage()
      {
          InitializeComponent();

          this.dataGrid.DataGridLoaded += DataGrid_DataGridLoaded;
      }

      private void DataGrid_DataGridLoaded(object? sender, EventArgs e)
      {
            this.dataGrid.BeginEdit(1, 0);
      }

  }
```

You can download this example on [GitHub](https://github.com/SyncfusionExamples/How-to-begin-editing-a-cell-on-initial-loading-in-.NET-MAUI-DataGrid).