# CityGlide API Doc

Endpoint : http://www.cityglide.com
Method : POST

#api_json.php

1. Get Bus Stop by Bus Number
	
	Parameter
	
		MODE: get_route_poly_inbound_outbound
		bus_lines: {{bus number}}
		
	Response
	
		{
			inbound:[
				locations_type_id : "2"
				latitude : "13.8109552"
				longitude : "100.547833"
				bound : "inbound"
				stop_id : "4345"
				stop_name : "อู่หมอชิต 2"
				stop_name_en : "Mochit 2 bus depot"
				priority : "1"
				routes_detail_statement : "4"
				routes_detail_station_priority : "1"
				end_station_invert : "อู่หมอชิต 2"
				start_station : "1"
				end_station : "46"
				center_station : 54.5
			],
			outbound:[]
		}
		
2. Get bus stop by Bus number and Bound

	Parameter
		
		MODE:get_route_poly
		bus_lines:50
		bound:{{number}} (1 = inbound, 2 = outbound)
	
	Response
	
		[
			{
				locations_type_id : "2"
				latitude : "13.8111137"
				longitude : "100.511098"
				bound : "inbound"
				stop_id : "5043"
				stop_name : "การไฟฟ้าฝ่ายผลิต"
				stop_name_en : "kan faifa fai phalit"
				priority : "1"
				routes_detail_statement : "2"
				routes_detail_station_priority : "1"
				start_station : "1"
				end_station : "46"
				center_station : 46
				end_station_invert : "การไฟฟ้าฝ่ายผลิต"
				count_station_invert : 48
			},
			{
				locations_type_id : "1"
				latitude : "13.809784726837828"
				longitude : "100.50972549326548"
				bound : "inbound"
				stop_id : "9072"
				stop_name : "ธนาคารกรุงเทพ สาขาบางกรวย"
				stop_name_en : "Bangkok Bank"
				priority : "2"
				routes_detail_statement : "2"
				routes_detail_station_priority : 0
			}
		]
		
#api.php

3. Get route by Busnumber and Bound

	Parameter
	
		MODE:get_route
		bus_line:50
		bound:1
		service_station:ข้างตลาดเตาปูน,แยกเตาปูน
		
	Response
	
		{
			start_station_inbound : "การไฟฟ้าฝ่ายผลิต"
			start_station_inbound_en : "Electric Generating Authority of Thailand"
			end_station_inbound : "สวนลุมพินีป้ายแรก"
			end_station_inbound_en : "Suan Lumpini 1st Bus Station"
			stop_id : "1258"
			routes_type_id : "1"
		}
		
4 Get Poly

	Parameter
	
		MODE:get_poly
		bus_lines:50
		bound:1
		stop_id:1258
		
	Response
	
		[
			{
				stop_name : "การไฟฟ้าฝ่ายผลิต"
				stop_name_en : "Electric Generating Authority of Thailand"
				latitude : "13.8111137"
				longitude : "100.511098"
				priority : "1"
				locations_type_id : "2"
			}
		]
		
5. Get marker

	Parameter
	
		bus_lines:50
		bound:1
		stop_id:1258
		MODE:get_marker
		
	Response
	
		[
			{
				stop_name : "การไฟฟ้าฝ่ายผลิต"
				stop_name_en : "Electric Generating Authority of Thailand"
				latitude : "13.8111137"
				longitude : "100.511098"
				priority : "1"
				routes_detail_station_priority : "1"
				azimute_start : ""
				azimute_end : ""
				origin_station : "no"
			}
		]

#api_html_en.php

6. Get Fast Bus
	
	get number of bus and infomation that will arrive to this stop_id
	
	Parameter
	
		MODE:get_fast_bus
		bus_line:50
		bound:1
		stop_id:1258
		
	Response
	
		[
			{
				duration : 1831
				distance : 3626
				duration_text : "30 Min."
				check_list_fast_bus : "00017A6A90CF | 17"
				distance_text : "3.6 km"
				priority : "17"
				service_lat : "13.821898"
				service_lng : "100.521606"
				service_id : "247"
				service_macaddress_gps : "00017A6A90CF"
				service_number : "12-5582"
				service_name : "50-55081"
				service_routes_id : "17"
				first_station : "การไฟฟ้าฝ่ายผลิต"
				last_station : "สวนลุมพินีป้ายแรก"
				first_station_en : "Electric Generating Authority of Thailand"
				last_station_en : "Suan Lumpini 1st Bus Station"
				choose_station : "ข้างตลาดเตาปูน,แยกเตาปูน"
				choose_station_en : "Tao Poon Intersection"
				time_arrival : "11:54"
				score : 0
				alert : ""
				alert_en : ""
			}
		]
		
#migrate_gps

7. Migrate GPS
	
	Parameter
		
		MODE:get_gps
		bus_lines:50
		bound:1
		stop_id:1258
		fastbus_num_id_1:247
		fastbus_num_id_2:0
		fastbus_num_id_3:0
		
	Response
	
		
