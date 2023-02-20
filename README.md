# IKR-1538

Скриншоты разработанных 3D моделей:
![IMG_20230214_223354_131](https://user-images.githubusercontent.com/125460099/219351149-6c1ed6d6-4e96-4bef-8fcb-b0e18e27f143.jpg)
![IMG_20230214_223353_937](https://user-images.githubusercontent.com/125460099/219351196-98a1bc5a-2b6d-4606-862a-c95660b7827d.jpg)
![IMG_20230214_223353_387](https://user-images.githubusercontent.com/125460099/219351216-7fdbdeae-0472-4c24-b4dd-5cdd3fe4374a.jpg)
![IMG_20230214_223354_194](https://user-images.githubusercontent.com/125460099/219351241-8c4bc79a-c5bd-4fc9-ad15-309d487c2107.jpg)

Код сайта:
<!DOCTYPE html>
<html>
	<head>
	
		<title>МойЦветок</title>
		<link href="eco_tag_nature_ecology_label_icon_191946.ico" rel="icon" type="image/x - icon"/>
		<style>
		body { background: url("https://wallbox.ru/wallpapers/main/201306/cvety-golubye-sinie-168e951.jpg"); color: #fff;
 }
 
        .button {
	     float: none;margin: 5px;width: 320px;height: 80px;border: solid 7px 	#20b2aa; border-radius: 20px; background-color: #e0ffff;line-height: 40px;font-size: 25px;text-align: center;
                }
	    .button1 {
	     float: right;margin: 5px;width: 320px;height: 80px;border: solid 7px 	#20b2aa; border-radius: 20px; background-color: #e0ffff;line-height: 40px;font-size: 25px;text-align: center;
                }
		.label {
	     float: none;margin: 40px;width: 200px;height: 100px;border: solid 3px 	#20b2aa; border-radius: 5px; background-color: #e0ffff;line-height: 40px;font-size: 20px;text-align: center;
                }
				
        </style>

		<script>
			var ledButt;
			var PumpButt;
			var AutoButt;
			var UvlButt;
			var WindButt;
			
			var tempButt;
			var tempLabel1;
			var tempLabel2;
			var tempLabel3;
			
            var HumButt;
			var HumLabel1;
			var HumLabel2;
			var HumLabel3;
			
			var LightButt;
			var LightLabel;
			
			var WaterButt;
			var WaterLabel1;
			var WaterLabel2;
			var WaterLabel3;

				
			window.onload = function () {
			
				ledButt = document.getElementById('ledButt');
				PumpButt = document.getElementById('PumpButt');
				AutoButt = document.getElementById('AutoButt');
				UvlButt = document.getElementById('UvlButt');
				WindButt = document.getElementById('WindButt');
				
				tempButt = document.getElementById('tempButt');
				tempLabel1 = document.getElementById('tempLabel1');
				tempLabel2 = document.getElementById('tempLabel2');
				tempLabel3 = document.getElementById('tempLabel3');
				
                HumButt = document.getElementById('HumButt');
				HumLabel1 = document.getElementById('HumLabel1');
				HumLabel2 = document.getElementById('HumLabel2');
				HumLabel3 = document.getElementById('HumLabel3');
				
				LightButt = document.getElementById('LightButt');
				LightLabel = document.getElementById('LightLabel');
				
				WaterButt = document.getElementById('WaterButt');
				WaterLabel1 = document.getElementById('WaterLabel1');
				WaterLabel2 = document.getElementById('WaterLabel2');
				WaterLabel3 = document.getElementById('WaterLabel3');

			}
			var onled = false;
			var onpump = false;
			var onauto = false;
			var onuvl = false;
			var onwind = false;
			
			
			var led = function(){
				onled = !onled;
				var xhr = new XMLHttpRequest();
				if (onled === true) {
					ledButt.innerHTML = 'Выключить свет';
					xhr.open('GET', 'led/on', true);
				} else {
					ledButt.innerHTML = 'Включить свет';
					xhr.open('GET', 'led/off', true);
				}
				xhr.send();
			}
			
			
			var pump = function(){
				onpump = !onpump;
				var xhr = new XMLHttpRequest();
				if (onpump === true) {
					PumpButt.innerHTML = 'Выключить полив';
					xhr.open('GET', 'pump/on', true);
				} else {
					PumpButt.innerHTML = 'Включить полив';
					xhr.open('GET', 'pump/off', true);
				}
				xhr.send();
			}
			
			var auto = function(){
				onauto = !onauto;
				var xhr = new XMLHttpRequest();
				if (onauto === true) {
					AutoButt.innerHTML = 'Выключить авторежим';
					xhr.open('GET', 'auto/on', true);
				} else {
					AutoButt.innerHTML = 'Включить авторежим';
					xhr.open('GET', 'auto/off', true);
				}
				xhr.send();
			}
			
			var uvl = function(){
				onuvl = !onuvl;
				var xhr = new XMLHttpRequest();
				if (onuvl === true) {
					UvlButt.innerHTML = 'Выключить увлажнитель';
					xhr.open('GET', 'uvl/on', true);
				} else {
					UvlButt.innerHTML = 'Включить увлажнитель';
					xhr.open('GET', 'uvl/off', true);
				}
				xhr.send();
			}			
			
			var wind = function(){
				onwind = !onwind;
				var xhr = new XMLHttpRequest();
				if (onwind === true) {
					WindButt.innerHTML = 'Закрыть форточку';
					xhr.open('GET', 'wind/on', true);
				} else {
					WindButt.innerHTML = 'Открыть форточку';
					xhr.open('GET', 'wind/off', true);
				}
				xhr.send();
			}
			var temp = function(){
				var xhr = new XMLHttpRequest();
				xhr.open('GET', 'temp', true);
				xhr.onload = function () {
					if (xhr.readyState === xhr.DONE) {
						if (xhr.status === 200) {
							tempLabel1.innerHTML = xhr.responseText;
							}
					}
				};
				xhr.send();
            }
					
            var Hum = function(){
				var xhr = new XMLHttpRequest();
				xhr.open('GET', 'Hum', true);
				xhr.onload = function () {
					if (xhr.readyState === xhr.DONE) {
						if (xhr.status === 200) {
							HumLabel1.innerHTML = xhr.responseText;
							}
					}
				};
				xhr.send();
			}
					
			var light = function(){
				var xhr = new XMLHttpRequest();
				xhr.open('GET', 'light', true);
				xhr.onload = function () {
					if (xhr.readyState === xhr.DONE) {
						if (xhr.status === 200) {
							LightLabel.innerHTML = xhr.responseText;
						}
					}
				};
				xhr.send();
            }
			
			var water = function(){
				var xhr = new XMLHttpRequest();
				xhr.open('GET', 'water', true);
				xhr.onload = function () {
					if (xhr.readyState === xhr.DONE) {
						if (xhr.status === 200) {
							WaterLabel1.innerHTML = xhr.responseText;
							}
					}
				};
				xhr.send();
            }

		</script>
		
	</head>
	
	
	<body bgcolor="#808000" style="font-family:'Trebuchet MS', Helvetica, sans-serif;">

		<p>
			<button class="button" onclick="auto()" id="AutoButt">Включить авторежим</button>
		</p>
		
		<p>
			<button class="button1" onclick="pump()" id="PumpButt">Включить полив</button>
		</p>
		
		<p>
			<button class="button" onclick="water()" id="WaterButt">Влажность почвы</button>
			<label class="label" style="color:	#2e2b57" id="WaterLabel1">?</label>
		</p>
		
		<p>
			<button class="button1" onclick="led()" id="ledButt">Включить свет</button>
		</p>
		
		<p>
			<button class="button" onclick="light()" id="LightButt">Освещенность</button>
			<label class="label" style="color:	#2e2b57" id="LightLabel">?</label>
		</p>
	
        <p>
			<button class="button1" onclick="uvl()" id="UvlButt">Включить увлажнитель</button>
		</p>	
		
		<p>
			<button class="button" onclick="temp()" id="tempButt">Температура воздуха</button>
			<label class="label" style="color:	#2e2b57" id="tempLabel1">?</label>
		</p>
		
		 <p>
			<button class="button1" onclick="wind()" id="WindButt">Открыть форточку</button>
		</p>	
		
        <p> 
			<button class="button" onclick="Hum()" id="HumButt">Влажность воздуха</button>
			<label class="label" style="color:	#2e2b57" id="HumLabel1">?</label>
		</p>
		
	
		
		</div>
    </section>
	<script src="http://ajax.googleapis.com/ajax/libs/jquery/1/jquery.min.js"></script>
	<script src="js/dm-modal.js"></script>
	</body>
</html>

