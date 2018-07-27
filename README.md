# Vue Google Picker
Vue.js button to open the dialog of files from Google Drive using Google Picker API

# Install
`npm install vue-google-picker --save-dev`

# Google API Loader
Include the Google API Loader in your static file
```
<script type="text/javascript" src="https://apis.google.com/js/api.js"></script>
```

# Attributes
* `config` - Keys and Credentials of Google API

# Events
* `picked` - When a file is picked. Return an object of selected files

# Use
Example:
```HTML
<template>
  <file-picker-button :config="gConfig" @picked="showDetails">
    Open Google Drive Dialog
  </file-picker-button>
</template>
<script>
import FilePickerButton from '../../vue-google-picker'
export default {
  components: {
    FilePickerButton
  },
  created() {
    this.gConfig = {
      // The Browser API key obtained from the Google API Console.
      developerKey: 'xxxxxxxYYYYYYYY-12345678',

      // The Client ID obtained from the Google API Console. Replace with your own Client ID.
      clientId: '1234567890-abcdefghijklmnopqrstuvwxyz.apps.googleusercontent.com',

      // Scope to use to access user's drive.
      scope: 'https://www.googleapis.com/auth/drive.file'
    }
  }, 
  methods: {
    showDetails (data) {
     if(data.picked === 'picked') {
      console.log(data.docs)
     }
    }
  }
}
</script>
```

# Other
All the information can be found on official Google Picker DOCS (https://developers.google.com/picker/docs/)



