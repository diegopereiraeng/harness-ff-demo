# FF Banking App UI

## FF DEMO/LAB

[The sample App](https://diegopereiraeng.github.io/html/index.html)

#### Clone the Code, Create the flags and add them to code:

### 1 - Build your App (RUNNING LOCALLY)

	BUILD=230
	docker build -t cv-demo-ui:$BUILD -f Dockerfile .
	docker run -it -p 8000:80 cv-demo-ui:$BUILD


### 3 - File where feature you want to add flags are [ff.js (html/js/ff.js)](https://github.com/diegopereiraeng/harness-ff-bankingapp-ui/blob/main/html/js/ff.js) 

### 4 - Flag the feature below

### ENABLE OR DISABLE HALLOWEEN MODE (DEPLOYED)
Use Harness Boolean FF to enable or disable Halloween mode.

	function Halloween(flag) {
        var halloweenElement = $("body").find("#Halloween");
        HalloweenMode = flag;
        console.log("Halloween: "+flag)
        if ( HalloweenMode == 'true'){
            console.log("Setting Halloween: "+flag)
            halloweenElement.attr("style","display: visibility;");
            $( 'body' ).each(function () {
                    backgroundBackup =$("body").css('backgroundColor');
                    this.style.setProperty( 'background-color', '#512888', 'important' );
                });
        else{
        $( 'body' ).each(function () {
            this.style.setProperty( 'background-color', backgroundBackup, 'important' );
        });
            halloweenElement.attr("style","display: none;");
        }
    }

### HALLOWEEN JACK (Optional)
Enable or Disable the Halloween Jack

	function HalloweenJack(flag) {
        var jack = $("body").find(".halloween");
        if(flag == 'true'){
            console.log("JAck In dA HouSe")
            jack.attr("style","display: visibility;");
        }else{
            jack.attr("style","display: none;");
        }
    }

### 5 - Build your app again

    BUILD=231
	docker build -t cv-demo-ui:$BUILD -f Dockerfile .
	docker run -it -p 8000:80 cv-demo-ui:$BUILD

### 6 - Go to [My Running Local Docker App](http://localhost:8000/index.html)

### 7 - Test your Flag in [Harness](https://app.harness.io)
