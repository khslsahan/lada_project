 <template>
  <div>
    <div class="jumbotron">
      <h1 class="display-4 text-center">X-Z Solutions</h1>
    </div>

    <div class="text-center container">
      <br />
       
        <fieldset>
          <center>
            <div class="form-group" style="width: 40%">
              <label for="device"></label>
              <select v-model="device" id="device" class="form-control">
                <option value="null" disabled>Select Device</option>
                <option>X</option>
                <option>Y</option>
                <option>Z</option>
              </select>
            </div>
          </center>
          <center>
            <div class="form-group" style="width: 40%">
              <label for="devicemodel"></label>
              <select id="devicemodel" v-model="devicemodel"  class="form-control">
                <option value="null" disabled >Select Device Model</option>
                <option>A</option>
                <option>B</option>
                <option>c</option>
              </select>
            </div>
          </center>
          <center>
            <div class="version" style="width: 40%">
              <label for="version"></label>
              <select id="version" v-model="version" class="form-control">
                <option value="null" disabled >Select Version</option>
                <option>1.0</option>
                <option>2.0</option>
                <option>3.0</option>
              </select>
            </div>
          </center>
          
        </fieldset>
       
      <button
            type="submit"
            class="btn btn-primary"
            @click='findBestApp'  
            style="margin-top: 40px"
          >
            Find Best App
          </button>
    </div>






    <div class="container">
      <div   v-show="show" >
        <h3 class="m-5"><b>Best Apps</b></h3>
        <div class="row">
          <div v-for="(item, index) in items" :key="index">
            <div class="card" style="width: 12rem; margin: 2rem">
              <img
                class="card-img-top"
                :src="getImgUrl(item.img)"
                alt="Card image cap"
              />
              <div class="card-body text-center">
                <h5 class="card-title text-center">App A</h5>
                <input type="button" class="btn btn-success" value="Install" />
              </div>
            </div>
          </div>
        </div>

        <h3 class="m-5"><b>Special Apps</b></h3>
        <div class="row">
          <div v-for="(item, index) in specialitems" :key="index">
            <div class="card" style="width: 12rem; margin: 1rem">
              <img
                class="card-img-top"
                :src="getImgUrl(item.img)"
                alt="Card image cap"
              />
              <div class="card-body text-center">
                <h5 class="card-title text-center">App A</h5>
                <input type="button" class="btn btn-success" value="Install" />
              </div>
            </div>
          </div>
        </div>
      </div>
      <div v-show="noresult" >
          <h3><b>No Any Result </b></h3>
      </div>

    </div>
  </div>
</template>
 
 <script>
export default {
  data() {
    return {
      device:null,
      devicemodel:null,
      version:null,
      show: false,
      noresult :false,
      items: [
        { img: "1578.png" },
        { img: "App A.png" },
        { img: "App B.png" },
        { img: "App C.png" },
        { img: "App D.png" },
        { img: "App E.jpg" },
      ],
      specialitems:[
        { img: "JB X.png" },
      ]
    };
  },
  methods: {
    getImgUrl: function (imagePath) {
      return require("@/assets/" + imagePath);
    },
    findBestApp(){
      this.show = false;
      this.noresult=false;
      if( this.device != null &&  this.devicemodel != null && this.version != null ){
          this.show =  true;
      }else{
          this.noresult = true;
      }
        
    }


  },
};
</script>
 
 <style>
</style>