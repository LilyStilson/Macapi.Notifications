<h1 align="center">Macapi.Notifications</h1>
<p align="center">Simplified macOS notification bridge for Delphi #DelphiCocoaFlavored</p>
<p align="center"><b>Lily Stilson // 2019 - 2020</b></p>
<hr>

## Usage
This unit is meant to be working with RAD Studio 10.4. It won't work in older versions due to bug in Macapi.Foundation.</p>

### SceduleNotification
Simplified notification sceduling. Fires notification after at a sceduled time;

```Pascal
procedure SceduleNotification(const ATitle, ASubtitile, AInformation: String; 
                              const ADeliveryDate: TDateTime; 
                              const UseTimeZone: boolean = True);
```

- **ATitle** - Notification title (Application name will be used, if empty)
- **ASubtitile** - Notification subtitle (Optional)
- **AInformation** - Notification body (Optional)
- **ADeliveryDate** - Notification delivery date
- **UseTimeZone** - Use PC's current time zone to fire notification (default = true)


### PresentNotification
Simplified notification presenting. Fires notification immediately.

```Pascal
procedure PresentNotification(const ATitle, ASubtitile, AInformation: String);
```

- **ATitle** - Notification title (Application name will be used, if empty)
- **ASubtitile** - Notification subtitle (Optional)
- **AInformation** - Notification body (Optional)


## Examples
```Pascal
// SceduleNotification // Form contains TButton.
procedure TNSNotificationsTestForm.SceduleNotificationButtonClick (Sender: TObject);
begin
  SceduleNotification('Notification Title', 'Foo Bar', 'Very Informative. Such Notification!', 
                      Now + EncodeTime(0, 0, 5, 0));
end;
```
```Pascal
// NSSavePanel // Form contains TButton and TEdit
procedure TNSNotificationsTestForm.PresentNotificationButtonClick (Sender: TObject);
begin
  PresentNotification('Notification Title', 'Foo Bar', 'Very Informative. Such Notification!');
end;
```

## Roadmap
- [ ] Notification click handler
