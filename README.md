<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Identity & Age Verification</title>
  <style>
    body { font-family: Arial; background: #f4f4f4; padding: 2rem; }
    .container { background: white; padding: 2rem; max-width: 500px; margin: auto; border-radius: 8px; }
    input, button { width: 100%; padding: 0.75rem; margin-top: 1rem; }
    button { background: #28a745; color: white; border: none; cursor: pointer; }
    .error { color: red; margin-top: 1rem; }
    .success { color: green; margin-top: 1rem; }
  </style>
</head>
<body>
  <div class="container">
    <h2>Get Identity and Age</h2>
    <form id="verifyForm">
      <label for="fullName">Full Name:</label>
      <input type="text" id="fullName"/>

      <label for="dob">Date of Birth:</label>
      <input type="date" id="dob"/>

      <label for="idNumber">Government ID Number:</label>
      <input type="text" id="idNumber"/>

      <button type="submit">Get Person Identity</button>
    </form>
    <p id="result"></p>
  </div>

  <script>


    document.getElementById("verifyForm").addEventListener("submit",async function(e) {
      e.preventDefault();
      try {
    // A hardcoded sample request is provided below.
    // This request would normally be built on your server.
        const mdocRequest = {
            "deviceRequest": "pGd2ZXJzaW9uYzEuMWtkb2NSZXF1ZXN0c4GhbGl0ZW1zUmVxdWVzdNgYWG6iZ2RvY1R5cGV1b3JnLmlzby4xODAxMy41LjEubURMam5hbWVTcGFjZXOhcW9yZy5pc28uMTgwMTMuNS4xpGhwb3J0cmFpdPVqZ2l2ZW5fbmFtZfVrYWdlX292ZXJfMjH0a2ZhbWlseV9uYW1l9W1yZWFkZXJBdXRoQWxsgYRDoQEmoRghWQF9MIIBeTCCASACCQCdvhptTdV7cDAKBggqhkjOPQQDAjBFMRowGAYDVQQKDBFUZXN0IE9yZ2FuaXphdGlvbjEnMCUGA1UEAwweVGVzdCBSZXF1ZXN0IEF1dGhlbnRpY2F0aW9uIENBMB4XDTI1MDUyNzIwNDgwMFoXDTM1MDUyNTIwNDgwMFowRTEaMBgGA1UECgwRVGVzdCBPcmdhbml6YXRpb24xJzAlBgNVBAMMHlRlc3QgUmVxdWVzdCBBdXRoZW50aWNhdGlvbiBDQTBZMBMGByqGSM49AgEGCCqGSM49AwEHA0IABIt9TGoAW2u25Yi_Czptq21xNUqolJdfvpBDRVBYdMXSsdwxsbl2JH3gF3YiP6VldwYI0UxF0-CtkgUCoJ-LjaMwCgYIKoZIzj0EAwIDRwAwRAIgR8Pa4-6_xvHi5m7SLckA0QmdjVhUEzeam_SHkpmM4AECIH5H7lgKOw0C0mFIvgGG8cyS7IUuk6wGIsmc7JjtX9em9lhApChXUdkLtAgRXpmq_RGHLXpfazSUYQ3mi5nXDYw73R9yqw_gyOSDvxpjwEeSKkHEdYt777Wu8OskvwjqAiPahXFkZXZpY2VSZXF1ZXN0SW5mb9gYWCehaHVzZUNhc2VzgaJpbWFuZGF0b3J59Wxkb2N1bWVudFNldHOBgQA",
            "encryptionInfo": "gmVkY2FwaaJlbm9uY2VYIPlv505ZK3Y93ZZhO-Wi4HqqHWHismrehHtGtNx3fxOxcnJlY2lwaWVudFB1YmxpY0tleaQBAiABIVggrlztqHsaR_OK3Npf8eTvG6AZWNxJsb69ZTFIPJcUR-0iWCCbWR3FyNPy2ysLKoiTysxI7LjxvcRnfNsB-JLDNmZdDw"
        }
        
        const request = {
            mediation: "required",
            digital: {
                requests: [{
                    protocol: "org-iso-mdoc",
                    data: mdocRequest
                }]
            }
        };
        console.log(request)
        
        const response = await navigator.credentials.get(request);
        // Send the response to your server for handling.
        consoole.log(response)

    } catch (error) {
        // Use an alternative identity verification method.
        console.log(error)
    }

     
      // Simulated success
    });
  </script>
</body>
</html>
