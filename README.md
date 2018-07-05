# Sign UP

To start managing your Events, Places, Voucher and Tickets you need to [Create an account](https://havefunhub.com/tickets.html ) 

Then [Login to Console](https://organiser.havefunhub.com) to generate a token to use in your requests when needed.

# Rest API

## curl
### events
```javascript
The below code will show events that are happening at any time:
curl -XGET -H "accept: application/json" "https://test.havefunhub.com/api/events/query?when=any"

The below code will show you all events:
curl -XGET -H “accept: application/json” “https://test.havefunhub.com/api/events/query”

The below code will show you events you made:
curl -XGET -H "accept; application/json" "https://test.havefunhub.com/api/events/query?user=your_username"

The below code will show all events wth promos linked to them:
curl -XGET -H "accept; application/json" "https://test.havefunhub.com/api/users/query?hasPromo=true"

The below code will show you all events without promo linked to them:
curl -XGET -H "accept; application/json" "https://test.havefunhub.com/api/users/query?hasPromo=false"

The below code will show you all events with a certain keyword in them:
curl -XGET -H "accept; application/json" "https://test.havefunhub.com/api/events/query?q= YOUR KEYWORD HERE"

The below code will show you events within a certain distance (km) from a chosen long and lat position:
curl -XGET -H "accept: application/json" "https://test.havefunhub.com/api/events/query?Lat=1&Long=1&Dist=100"





```

Check our [API explorer](https://havefunhub.com/api-doc) for the available end points. You can consume services from your any client.
```javascript
$.ajax({
  url: 'https://havefunhub.com/api/events/query',
  dataType: "json",
  ...
  success: function (data) {
                  //do something with Events' JSON result
           }
})
```
# Java API

Soon. Working on it :) 

## Requirements

Java 1.7 or later

## Installation

### Maven users

Add this dependency to your project's POM:

```xml
<dependency>
  <groupId>com.druidalabs</groupId>
  <artifactId>havefunhub-api</artifactId>
  <version>3.0.0</version>
</dependency>
```
## Documentation

Please see the [Java API docs](http://druidalabs.com) for the most up-to-date documentation.

## Usage

HaveFunHubExample.java

```java
import java.util.HashMap;
import java.util.Map;

public class HaveFunHubExample {

    public static void main(String[] args) {
        RequestOptions requestOptions = (new RequestOptionsBuilder()).setApiKey("YOUR-SECRET-KEY").build();
        Map<String, Object> eventsMap = new HashMap<String, Object>();
        eventsMap.put("Lat", 34.6037); 
        eventsMap.put("Long", 58.3816);
        eventsMap.put("when", "now");
        try {
            ArrayList<Event> events = Event.query(eventsMap, requestOptions);
            System.out.println(events);
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

## Entities
### Events
### Places
### Promotions
### Tickets
