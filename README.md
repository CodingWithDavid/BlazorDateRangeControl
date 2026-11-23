# DateRangePresets

A small .NET 11 Blazor WebAssembly application demonstrating an accessible date-range picker for timesheet history, audit logs, release lists, and similar data views.

## Features

- Today, Last 7 days, and This month shortcuts
- Custom From and Through dates
- Draft-first selection: changes do not refresh results until Apply is pressed
- Inclusive date ranges
- Inline validation for missing or reversed dates
- Parent-owned query callback through `EventCallback`
- Native date controls with no JavaScript or third-party dependencies
- Responsive UI based on the supplied navy, blue, teal, amber, and neutral palette

## Requirements

- .NET SDK 11.0 or later

## Run locally

```powershell
dotnet run --project .\DateRangePresets.csproj
```

Then open the local URL shown by the .NET host.

## Build

```powershell
dotnet build .\DateRangePresets.slnx
```

## Project structure

- `Pages/Home.razor` — demo page and timesheet history
- `Components/DateRangePresets.razor` — reusable date-range picker
- `Components/DateRangePresets.razor.css` — component-scoped styles
- `Layout/` — branded application shell and navigation
- `wwwroot/css/app.css` — global design tokens and base styles

## Component usage

```razor
<DateRangePresets
    Label="Date range"
    Today="@_today"
    OnApply="ApplyRange" />
```

The parent supplies the business date explicitly and receives an inclusive `Range` containing `From` and `Through` when Apply succeeds.
