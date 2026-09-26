# Hotel dataset

The Hotel MCP Server doesn't call a live booking API. Free hotel APIs with real availability are hard to find, so the `check_hotel_availability` tool reads from a hard-coded list inside its Code Tool node instead.

The list covers 40 destinations with three hotels each (120 in total), one per budget tier. Each price is in the local currency of that destination.

To add a destination, open the `check_hotel_availability` node in [`hotel-mcp-server.json`](../workflows/mcp-servers/hotel-mcp-server.json) and add three objects to the `hotels` array in this shape:

```javascript
{ name: "Hotel Name", location: "City", price: 3500, currency: "BDT", type: "mid-range" }
```

`type` has to be exactly `budget`, `mid-range`, or `luxury`, because the tool compares it against the budget the agent passes in.

## Bangladesh (20 destinations)

| Destination | Currency | Budget | Mid-range | Luxury |
| --- | --- | --- | --- | --- |
| Cox's Bazar | BDT | Hotel Al-Amin (1,200) | Hotel Sayeman (3,800) | Sea Pearl Beach Resort (8,500) |
| Sajek Valley | BDT | Sajek Meghpuri Resort (2,000) | Runmoy Resort (4,200) | Sajek Heaven Resort (7,000) |
| Bandarban | BDT | Hillview Guest House (1,500) | Hillside Resort (3,200) | Nilgiri Hills Resort (6,500) |
| Sylhet | BDT | Sylhet City Inn (1,800) | Grand Sylhet Hotel (4,000) | Rose View Hotel (7,500) |
| Sreemangal | BDT | Nishorgo Eco Cottage (1,600) | Sreemangal Nirvana Resort (3,500) | Tea Resort Sreemangal (6,000) |
| Kuakata | BDT | Kuakata Guest Inn (1,400) | Kuakata Sea View Resort (3,300) | Kuakata Grand Hotel (5,500) |
| Rangamati | BDT | Rangamati Lake View Lodge (1,700) | Rangamati Hill Resort (3,600) | Parjatan Motel Rangamati (5,800) |
| Saint Martin's Island | BDT | Coral View Guest House (2,200) | St. Martin's Sea View Resort (4,800) | Blue Marine Resort (9,000) |
| Khagrachari | BDT | Khagrachari Hill Lodge (1,300) | Khagrachari Comfort Inn (3,200) | Khagrachari Resort (5,200) |
| Jaflong | BDT | Jaflong River View Cottage (1,500) | Jaflong Riverside Resort (3,400) | Jaflong Panorama Resort (5,900) |
| Bisanakandi | BDT | Bisanakandi Riverside Guest House (1,400) | Bisanakandi Comfort Resort (3,100) | Bisanakandi Premium Resort (5,000) |
| Ratargul | BDT | Ratargul Wetland Lodge (1,300) | Ratargul Comfort Cottage (3,000) | Ratargul Nature Resort (4,800) |
| Panchagarh | BDT | Panchagarh Traveler's Inn (1,200) | Panchagarh City Hotel (2,800) | Panchagarh Grand Lodge (4,500) |
| Nilgiri | BDT | Nilgiri Basecamp Cottage (1,600) | Nilgiri Valley Resort (3,700) | Nilgiri Cloud Resort (6,200) |
| Chittagong | BDT | Agrabad City Hotel (2,000) | Golden Inn Chittagong (5,500) | Radisson Blu Chittagong Bay View (12,000) |
| Rangpur | BDT | Rangpur Inn (1,400) | Rangpur City Hotel (3,000) | Rangpur Grand Hotel (5,000) |
| Dhaka | BDT | Dhaka Budget Inn (1,800) | Six Seasons Hotel Dhaka (7,000) | InterContinental Dhaka (18,000) |
| Mymensingh | BDT | Mymensingh City Hotel (1,300) | Mymensingh Comfort Inn (2,900) | Mymensingh Grand Lodge (4,700) |
| Comilla | BDT | Comilla Comfort Inn (1,400) | Comilla City Hotel (3,000) | Comilla Palace Hotel (5,100) |
| Barisal | BDT | Barisal River Side Inn (1,500) | Barisal Comfort Hotel (3,100) | Barisal Grand Resort (5,300) |

## International (20 destinations)

| Destination | Currency | Budget | Mid-range | Luxury |
| --- | --- | --- | --- | --- |
| Kathmandu | NPR | Kathmandu Guest House (4,500) | Hotel Yak & Yeti (9,500) | Hyatt Regency Kathmandu (15,000) |
| Pokhara | NPR | Pokhara Lakeside Hostel (3,000) | Temple Tree Resort Pokhara (7,500) | Fish Tail Lodge Pokhara (13,000) |
| Bangkok | THB | Bangkok Backpacker Inn (800) | Novotel Bangkok Sukhumvit (3,500) | Mandarin Oriental Bangkok (15,000) |
| Phuket | THB | Phuket Beach Hostel (900) | Novotel Phuket Resort (4,500) | Amanpuri Phuket (30,000) |
| Bali | IDR | Bali Budget Homestay (250,000) | Ibis Styles Bali (900,000) | Four Seasons Resort Bali (8,000,000) |
| Singapore | SGD | Singapore Hostel Central (60) | Ibis Singapore Novena (180) | Marina Bay Sands (700) |
| Kuala Lumpur | MYR | KL Backpacker Lodge (90) | Ibis KL City Centre (250) | Petronas Grand Hyatt (900) |
| Dubai | AED | Dubai Budget Suites (250) | Ibis Dubai Al Barsha (600) | Burj Al Arab (6,000) |
| Istanbul | TRY | Istanbul Old City Hostel (500) | Novotel Istanbul (2,200) | Ciragan Palace Kempinski (8,000) |
| Paris | EUR | Paris Budget Hotel (70) | Novotel Paris Centre (200) | The Ritz Paris (1,200) |
| London | GBP | London Traveler Hostel (60) | Premier Inn London (150) | The Savoy London (900) |
| New York | USD | New York City Budget Inn (100) | Holiday Inn Manhattan (280) | The Plaza New York (1,000) |
| Tokyo | JPY | Tokyo Capsule Hotel (5,000) | Mitsui Garden Hotel Tokyo (20,000) | Park Hyatt Tokyo (90,000) |
| Maldives | USD | Maldives Budget Guesthouse (100) | Kurumba Maldives (600) | Soneva Fushi Maldives (3,000) |
| Colombo | LKR | Colombo City Hostel (3,000) | Cinnamon Red Colombo (15,000) | Shangri-La Colombo (45,000) |
| Delhi | INR | Delhi Budget Stay (1,500) | Lemon Tree Premier Delhi (7,000) | The Leela Palace Delhi (25,000) |
| Goa | INR | Goa Beach Hostel (1,200) | Novotel Goa Resort (6,500) | Taj Exotica Goa (18,000) |
| Kolkata | INR | Kolkata Budget Lodge (1,400) | Ibis Kolkata Rajarhat (5,000) | The Oberoi Grand Kolkata (15,000) |
| Darjeeling | INR | Darjeeling Hill Homestay (1,500) | Sinclairs Darjeeling (5,500) | Mayfair Darjeeling (12,000) |
| Sydney | AUD | Sydney Backpacker Hostel (40) | Ibis Sydney Darling Harbour (200) | Park Hyatt Sydney (900) |

## How matching works

The tool lowercases both the location the agent sends and each hotel's location, then keeps a hotel if either string contains the other. So "cox's bazar", "Cox's Bazar", and "Cox's Bazar beach" all match the Cox's Bazar entries. A budget, if one is given, is then matched exactly against `type`.

If nothing matches, the tool returns a short message in Bangla saying no hotel was found for that location and budget, and the agent tells the user.
