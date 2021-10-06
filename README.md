# FF Banking App UI

## FF DEMO/LAB

[The sample App](https://diegopereiraeng.github.io/html/index.html)

#### Clone the Code, Create the flags and add them to code:

### 1 - Build your App (RUNNING LOCALLY)

Run these commands in the repo folder:

	BUILD=230
	docker build -t cv-demo-ui:$BUILD -f Dockerfile .
	docker run -it -p 8000:80 cv-demo-ui:$BUILD

### 2 - Go to [My Running Local Docker App](http://localhost:8000/index.html)

### 3 - LOGIN PAGE HTML File location [index.html (html/index.html)](./html/index.html)

### 4 - File where features you want to add flags in javascript are [ff.js (html/js/ff.js)](./html/js/ff.js) 

### 5 - Flag the feature below or any other feature you want.

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
