<template>
  <!-- 導入すると表示崩れるので、一旦導入しない -->
  <v-container fluid fill-height>
    <v-row style="height: 100px;" justify="center">
      <h1>topic</h1>
    </v-row>
    <v-row style="height: 100px;" justify="center" align-content="center">
      <v-col cols="3" v-for="value in cards" :key="value.title">
        <v-card>
          <v-img :src="value.src" class="black--text align-end" height="200px"></v-img>
          <v-card-subtitle class="pb-0">{{value.genre}}</v-card-subtitle>
          <v-card-text class="text--primary">
            <div>{{value.title}}</div>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>

    <v-row style="height: 300px;" justify="center" align-content="center">
      <v-card class="mx-auto grey lighten-2" max-width="344" outlined>
        <!-- この辺カードに良い感じにする -->
        <h2>more...</h2>
      </v-card>
    </v-row>
  </v-container>
</template>
<script>
export default {
  data: () => ({
    cards: [
      {
        title: "pythonの記事",
        src:
          "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOEAAADhCAMAAAAJbSJIAAAAtFBMVEX////4xj03fvD4xDItevD74J+JrvQedO/l7/35zFL4xTj73JAwe/CXtvYrePCNsvadvPb4wyz//fj4yUj++u7y9/5DhfHT4fv///797cj5/P///ff4yUn4yEL74aFUjfK80fmux/j62If85rP98dT5zl5kmPOBqvVKiPE7gfBwn/PM3PpVj/K1zfnf6fz+9d/51Hf85az86sD+9+f5zlsMb+92o/T61HVom/PF1/r50Wn97s0w4eoQAAAImklEQVR4nO2dCVPiMBSALeWMtRJuURRQTpFLVgX+///aXlhahSYvgReZfDM7s4N75PPlzku8utJoNBqNRqPRaDQajUaj0Wg0GvVoNqsuzSZ2QaSTr7eLg3H/aTisjUaj2nD41B8Piu16HrtgMsi3b/pW2rbttGVZqR3O7/3P+jftv6yZbw9qOUcjdRhHNDcctKvYRYWQ73xZdvqIXEjatr46fy2Ur2PLPha7H7G0rfErdqHZab6Ncjx6gWRu9IZdckY6NZtbz8eudbALz8DrBOrnxtGe1LEFkhhwNb/fHLPYCkepgytoiF1TOIxtSyyAuzCusUUO0REPoI+taIfzlpMkmErllBw3XiMRtNJHZ2uJigoO/9XanpEzQ8nejlPwWmuN1FthDUKddOrNK1+zPQI7pgfYQnHy/8LC9cPv/xiuOEW0+Y3B9zLCmux/PmZbXvzEVi2IYdFykXVQFRrDlGItsf5dG+3b6FeK0HqaU2tqEw728YLloaOkrdaYWAybW3xHAryUKqKYHOL222MYbz41oGH6BsXkEKHhKB5D6NRGWUM7tqXUhLZDdQ1j64I2tB0qa5iqRb8yubhamrIjJYOvGdU1jAxkbeikTWnDlJ0N+tPmjcCqX2XDVNrKruv19a3AAlFxQ/coIpdjPLX4o4YS0IZnRhtqQ22Ijzb8+4bZfzlGmJcaihlW86yMWRUVM2TnQxtqQ+VR2bD62rnJinI7ZBQMDJfd658stpUT+E0/Rs6KTxxWwcAwQ81foK35TLJfcyy4nuUnMDSNXyF0fi9T8FVoP0LE8PqAoWGYxlae4JtgotNJDJ0wLmUJSsuTkWtoGPRZjmBbXp6MZEOD3skQrJ+7i9kZFpMNDSqhS20+IbRBF/+EtHvckBQawoZZlEYYGpKjhoZ5LSpY/5dclhMZesd0CTF06umLoCH4cEyS4TwhhgbpiQm+YdVRZkNDbFRsDtFCGBh+Jhoaxh8NYXAMyWAoFESskSI03CQbkhVcsI4zmwkM14yGIt0p877YKfDTx3oMhqQLFaxihjDIcWQxNAzokh+zn3HmpV4ywIrFELzG+MKspNaTV4YCiyGZwwThya8yCBK9mSqpQUsgQ3C+lhTstluGEmUzhK0Ts0gLwwCvo3lhMwSuMPAm3Q7Wl1eGhAXwDlKGCOZRQ+hX0kaLSdAJ4jvAcI3ZDIOedMlWSYENsYgZw5x/QY9tvHdjmAEYYk7ZglspW9YQGuQTYDjCE0xZU74QgnakMCelQYbqM3MIHfi7mimeYXDliXG09wFsnOLNaOyxX4LkLZp9Q/7OFOewwhX88AtwzRNCw1xwG94iDRa5QJCrEYLmbR8ohtbuusYdn6Bh8q/z+xjDoT0Jbo6yj4QBgCXi+XdKLbu2u8ewZJtw7xtuuA2ll/8wbgKDbef6b7trbwveCLpbitxDvpCNU+B0alQLGH7z5DJx6Lt8fX2NHT4csp29l5Qy/ILOpIZ7mQ+upJY96t+s69N8tenD+R+/bwCCEENgV2rl+muhd60WhLsNepTPY2jZY7Fr9HcFSABdWtzpNRBDwReCKs8FyjNTE4whoB1G7yY3Go2Sw71PJeT+vtSIdnyV95flY3djwv3O0tNYVhjAu26v8OBT9mkFGM6vsvNxoVBYrXq93mrl/K5FKDVNuB7MkHcBnJ7sOphZ16QmcTlcnigiart/kX885JzT2JNgVHjvUlhnKGjIP6fhm5daT4Hgo4HhB5qXcq0trOAWfuMT2tkLG/KvLbjWh2m/k3l/wAmgAVof8qzxg0XduyGjzwAa8q/xOba8g93N+xaeoEH502k59tpy3kytxHSYeTJD/r029vcsrL73FxiPiU4F4Cif+dUVP2mC8aTvRICyMFnPLayh98cfMOso7NyC9YGntPccJ+/emGTMR4DhmrEhMmdnnRJAV8p+Bmy7TxxWcLsZwwTlDDGe43tjxQuuISlABFnnbWk3aYL5OPo0AHMxGGc1lgKGwHwaxpwoz5DzHEW6IfBOAuOIiG9oAvPaWA9J8Q3BedCMU1N8Q/690h0Dpt7UNVxgjhaAs8MdTHneI3RDketdLIO+t0WDaSh0a4ZlSPQMHxENxS4hMgQR25A8iAiyDBg11/DQleszIHqPNHljGNkQsNkdZZp4/xDZUPyebOJS3zNE24aikMTSGEmdzRDTUPR+pcc0IYaYhgSU3/2DhJkNpqHwJeCA4+M+oqEp7dmI9bGfH+M94I1hSEyJT39Mh4fDiGVoFuQ+UXN78KeqoBgS07wWf00hSvXmyf6VmmuY+DDAftmEobRwfYp3lK6m7U7xJx2uGJLNY0aUxXImO37JMBuCDhhUQBtqQ/XRhiHlAiMPan0vOEZ8wgjoSuHpOMGcRhueGW2oDbUhPtrwOIR6RJOOLsmQ9pbOerayjF54uhxDQr53zJb7FxMux9Dc21CaXWIMo3kUeymOl2IYPxwL39i7FMN4Kkx4xflSDElsV7BxcYYP8WSfS6ulpBA3/P6SYobgXIx4Lb0Kayn/LZhTAs5riydoh5caZD1HLgnwbYv4rbrw7WcZT3XLBCgYP8YN88VJ+fxnE0eBDxetvZZYCe9OiT/ULZkKOMGUPHxXx1k5nHnLyUGQCXxmSmj3peEw6+6tEJULodjlPJMaq1Vr/4a0jPfypTMTW+ZHvz+qdaQ+3O8CHUbOz62Qz1Lg1Yd9iLw8Gdm8SLnqTIikTKdT8L4Sr6m0p9w4ESEjWFMJVevY8BdmnyJvsNCN2gH0uesBHQntKdqH/mC7ArxvYtKexEy8kzO7bnFJEtq6VnKQP8L9XbdMmd4NIiYtd++k/py4c3G/zfSo+9zQETmT0k1m+yf1AkrbxbzsephmNNPC+6g8X2xhT+IrRmm2fc505xv/3avCqreZdzPP29lFyMVplBRcFmk0Go1Go9FoNBqNRqPRaDQazdXVfwjeA1Y5/KttAAAAAElFTkSuQmCC",
        genre: "python"
      },
      {
        title: "go言語系のなんかの記事",
        src:
          "data:image/png;base64,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",
        genre: "go"
      },
      {
        title: "vueの適当な、なんかの記事",
        src: "https://jp.vuejs.org/images/logo.png",
        genre: "vue"
      }
    ]
  })
};
</script>