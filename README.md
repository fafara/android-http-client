**Android HTTP Client**

Android Http Client It is a small library to make requests to any internet service simple and practical way.
You can implement multiple interfaces for the management of the responses. It also includes interfaces
for managing upload and download of files.

Example:

         Request request = Request.create("http://service.server.com/getData");
         request.setMethod("POST")
                 .setTimeout(120) //2 Minutes
                 .addHeader("Authorization", "Key=MY_SERVICE_KEY")
                 .addParameter("key1", "value1")
                 .addParameter("key2", "value3")
                 .addParameter(new Parameter("key3", "value3"))
                 .addParameter("file", new File(""))
                 .setFileUploadListener(new FileUploadListener() {
                     @Override
                     public void onUploadingFile(File file, long size, long uploaded) {

                     }
                 })
                 .setRequestStateListener(new RequestStateListener() {
                     @Override
                     public void onStart() {

                     }

                     @Override
                     public void onFinish() {

                     }
                 })
                 .setResponseListener(new JsonResponseListener() {
                     @Override
                     public void onOkResponse(JSONObject jsonObject) throws JSONException {

                     }

                     @Override
                     public void onErrorResponse(JSONObject jsonObject) throws JSONException {

                     }

                     @Override
                     public void onParseError(JSONException e) {

                     }
                 }).execute();
