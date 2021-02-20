 <template>
  <div>
    <div class="jumbotron">
      <h1 class="display-4 text-center">X-Z Solutions</h1>
    </div>

    <div class="text-center container">
      <br />
      <form>
        <fieldset>
          <center>
            <div class="form-group" style="width: 40%">
              <label for="device"></label>
              <select id="device" class="form-control">
                <option>Select Device</option>
                <option>X</option>
                <option>Y</option>
                <option>Z</option>
              </select>
            </div>
          </center>
          <center>
            <div class="form-group" style="width: 40%">
              <label for="devicemodel"></label>
              <select id="devicemodel" class="form-control">
                <option>Select Device Model</option>
                <option>A</option>
                <option>B</option>
                <option>c</option>
              </select>
            </div>
          </center>
          <center>
            <div class="version" style="width: 40%">
              <label for="version"></label>
              <select id="version" class="form-control">
                <option>Select Version</option>
                <option>1.0</option>
                <option>2.0</option>
                <option>3.0</option>
              </select>
            </div>
          </center>
          <button
            type="submit"
            class="btn btn-primary"
            style="margin-top: 40px"
          >
            Find Best App
          </button>
        </fieldset>
      </form>
    </div>

    <div class="container">
      <h3 class="m-5">Best Apps</h3>
      <div class="row">
        <div v-for="(item, index) in items" :key="index">
          <div class="card" style="width: 12rem; margin: 1rem">
            <img
              class="card-img-top"
              src="../assets/1578.png"
              alt="Card image cap"
            />
            <div class="card-body text-center">
              <h5 class="card-title text-center">App A</h5>
              <input type="button" class="btn btn-success" value="Install" />
            </div>
          </div>
        </div>
      </div>

      <h3 class="m-5">Select Apps</h3>
      <div class="row">
        <div v-for="(item, index) in items" :key="index">
          <div class="card" style="width: 12rem; margin: 1rem">
         
           
          
            <img
              class="card-img-top"
              :src= "item.img"
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
  </div>
</template>
 
 <script>
export default {
  data() {
    return {
      items: [
        { img: "../assets/1578.png" },
        { img: "../assets/App A.png" },
        { img: "../assets/App B.png" },
        { img: "../assets/App C.png" },
        { img: "../assets/App D.png" },
        { img: "../assets/App E.jpg" },
      ],
    };
  },
};
</script>
 
 <style>
</style>