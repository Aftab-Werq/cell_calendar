# cell_calendar

[(https://img.shields.io/pub/v/cell_calendar.svg)](https://pub.dev/packages/cell_calendar)

Full screen calendar widget with useful features. Inspired by the UI of Google calendar

## Usage

- **Events**

You can show the events in calendar by inserting list of CalendarEvent as `events`
```dart
    CellCalendar(
      events:[
        CalendarEvent(eventName: "Hello World",eventDate: DateTime1),
        CalendarEvent(eventName: "Hello World",eventDate: DateTime2),
      ]
    );
```

If you need to customize the calendar more, the additional parameters like `eventBackGroundColor`, `eventTextColor` and `eventID` are helpful.


- **onPageChanged**

The callback `onPageChanged` is literally called when the current page is changed.
```dart
    CellCalendar(
      onPageChanged: (firstDate, lastDate){
        print("This is the first date of the new page: $firstDate");
        print("This is the last date of the new page: $lastDate");
      }
    );
```
In this sample code, `firstDate` is the date in the very first cell of the new page, and the logic is same as `lastDate`.

- **onCellTapped**

The callback `onCellTapped` is called when user tapped a cell.
```dart
    CellCalendar(
      onCellTapped: (date){
        print("$date is tapped !");
      }
    );
```
It is called with tapped DateTime, so you can get the events on the date if you want.
```dart
    CellCalendar(
      onCellTapped: (date){
        print("$date is tapped !");
        final eventsOnTheDate = sampleEvents().where((event) {
          final eventDate = event.eventDate;
          return eventDate.year == date.year &&
              eventDate.month == date.month &&
              eventDate.day == date.day;
        }).toList();
      }
    );

```

If you have any requests or questions, please feel free to create a new issue on [github](https://github.com/santa112358/cell_calendar/issues).

