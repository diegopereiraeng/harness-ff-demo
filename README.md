# FF Banking App UI

## FF DEMO/LAB

#### Create the flags and add them to code:

### 1 - Build your App (RUNNING LOCALLY)

	BUILD=230
	docker build -t cv-demo-ui:$BUILD -f Dockerfile .
	docker run -it -p 8000:80 cv-demo-ui:$BUILD


### 2 - Go to Harness and Create a Project + Flag + Environment + SDK Key

### 3 - Edit the [ff.js (html/js/ff.js)](https://github.com/diegopereiraeng/harness-ff-bankingapp-ui/blob/main/html/js/ff.js) file and initialize the SDK code:

### 4 - Add your FEATURE =D

in code look for:

----> ADD Your FEATURES HERE <--------


(Suggested Features):

If you are using the suggested features, Create the flags using the same name of suggested functions below.

ex: function Halloween(flag)...
flag name in Harness will be "Halloween"

### ENABLE OR DISABLE HALLOWEEN MODE (DEPLOYED)
Use Harness Boolean FF to enable or disable Halloween mode.

Flag: Halloween

Type: Boolean

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

### HALLOWEEN JACK
Enable or Disable the Halloween Jack

Flag: HalloweenJack

Type: Boolean

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