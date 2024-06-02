let inp=document.querySelector('.inp');
let btn=document.querySelector('.btn');
let form=document.querySelector('form');
let list=document.querySelector('.weatherList');
let place=document.querySelector('.place');


function Display(content){

    let li=document.createElement('li');
    li.classList.add('info');
    li.innerHTML=`
    <div class="info-head">${content[0]}</div>
    <div class="info-text">${content[1]}</div>            
    `;

    list.appendChild(li);
    inp.value='';
}

function abc(city){
    let api=YOUR_API_KEY;
    let geo=`http://api.openweathermap.org/geo/1.0/direct?q=${city}&appid=${api}`;
    return new Promise(async (resolve,reject)=>{
        try{
            let {data}=await axios.get(geo);
            data=data[0];
            const {lat,lon}=data;
            let weather=await axios.get(`https://api.openweathermap.org/data/2.5/weather?lat=${lat}&lon=${lon}&appid=${api}`);
            console.log(weather);
            resolve(weather.data);
        }
        catch(err){
            reject(err);
        }
    })
}


// FUNCTION TO CONVERT UTC TIME IN 12 HR
function ConvertTime(tm)
{
    let dateObj = new Date(tm * 1000);
    // let localString = dateObj.toLocaleString([],{hour:'2-digit',minute:'2-digit'});
    let localString = dateObj.toLocaleString();
    let local_tm = localString.slice(11,21);
    return local_tm;
}
//////////////////////////////////////////////////////////


btn.addEventListener('click',(ev)=>{
    // console.log(ev);
    ev.preventDefault();
    let city=inp.value;
    abc(city)
        .then((d)=>{
            list.innerText='';
            place.innerText=inp.value.toUpperCase();

            // Highlight
            let desc=["Highlight",d.weather[0].description];
            Display(desc);


            // Sunrise
            let sunrise=["Sun Rise",ConvertTime(d.sys.sunrise)];
            Display(sunrise);

            // Sunset
            let sunset=["Sun Set",ConvertTime(d.sys.sunset)];
            Display(sunset);

            // Temperature
            let temp=["Temperature",d.main.temp];
            Display(temp);

            // Pressure
            let press_unit=(d.main.pressure)*0.1;
            let press=["Pressure",(press_unit.toFixed(2))+" kPa"];
            Display(press);

            // Humidity
            let humid=["Humidity",d.main.humidity+" %"];
            Display(humid);

            // Wind Speed
            let wind=["Wind Speed",d.wind.speed+" m/sec"];
            Display(wind);

            // Clouds
            let clouds=["Cloudy",d.clouds.all+" %"];
            Display(clouds);

        })
        .catch((err)=>{
            alert(err);
        })
})
