<script setup>
export default {
  data() {
    return {
      name: null,
      email: null,
      subject: null,
      message: null,
    };
  },
  methods: {
    async Sendform() {
      try {
        let response = await this.$axios.$post("/api/main/contact/", {
          contact: this.name,
          email: this.email,
          message: this.message,
        });
        this.$toast.success("Mensaje enviado con exito");
      } catch (e) {
        this.$toast.error(e);
      }
    },
  },
};
</script>

<template>
  <div>
    <Header />
    <div class="contact p-5 pb-20 lg:p-0">
      <div class="hero-container">
        <div class="hero lg:w-1/2 lg:-ml-20 lg:relative lg:h-72">
          <div class="text lg:absolute lg:left-0 lg:bottom-0 w-90 lg:ml-10">
            <div
              class="font-bold uppercase text-white text-4xl lg:mt-14 lg:mb-10 mb-5"
            >
              Excelentes ideas pueden salir de esto
            </div>
            <div class="text-white uppercase text-sm lg:mb-0 mb-7">
              <span class="font-bold">ESCRÍBENOS</span> Y NOS CONTACTAREMOS
              CONTIGOs
            </div>
          </div>
        </div>
      </div>
      <div class="lg:bg-white">
        <form class="mx-auto lg:w-5/12 lg:mt-10 lg:mb-36">
          <div class="lg:flex lg:mb-4">
            <div class="flex">
              <label
                for="name"
                class="lg:visible invisible lg:h-auto w-0 h-0 lg:w-14 text-right text-sm capitalize text-gray mt-2.5"
                >Nombre</label
              >
              <input
                class="input-text bg-gray rounded-sm lg:mr-3 lg:ml-2 h-10 lg:mb-0 mb-7 px-2"
                placeholder="Nombre"
                type="text"
                id="name"
                name="name"
                v-model="name"
              />
            </div>
            <div class="flex">
              <label
                for="email"
                class="lg:visible invisible lg:w-auto lg:h-auto w-0 h-0 text-right whitespace-nowrap lg:ml-2 text-sm capitalize text-gray mt-2.5"
                >Correo Eléctronico</label
              >
              <input
                class="input-text bg-gray rounded-sm h-10 lg:ml-2 lg:mb-0 mb-7 px-2"
                placeholder="Correo Eléctronico"
                type="text"
                id="email"
                name="email"
                v-model="email"
              />
            </div>
          </div>
          <div class="flex mb-4">
            <label
              for="affair"
              class="lg:visible invisible h-0 w-0 lg:h-auto lg:w-14 block text-sm capitalize text-gray mt-2.5 text-right"
              >Asunto</label
            >
            <input
              class="bg-gray input-box rounded-sm h-10 lg:ml-2 lg:mb-0 mb-4 px-2"
              placeholder="Asunto"
              type="text"
              id="affair"
              name="affair"
              v-model="subject"
            />
          </div>
          <div class="flex lg:mb-10">
            <label
              for="message"
              class="lg:visible invisible lg:h-auto w-0 h-0 text-right lg:w-14 block text-sm capitalize text-gray lg:mt-2.5"
              >mensaje</label
            >
            <textarea
              class="bg-gray input-box rounded-sm lg:ml-2 message lg:mb-0 mb-3 px-2 lg:py-0 py-2"
              placeholder="Mensaje"
              id="message"
              name="message"
              v-model="message"
            ></textarea>
          </div>
          <div class="lg:-mr-9">
            <div class="flex float-right">
              <NuxtLink to="/"
                ><button
                  class="lg:visible invisible w-0 h-0 uppercase rounded-sm border-blue-green font-bold text-sm uppercase tracking-widest-1 text-blue-green lg:w-36 lg:h-10 mr-10 return text-right pr-5"
                >
                  VOLVER
                </button></NuxtLink
              >
              <button
                class="uppercase rounded-sm border-blue-green bg-blue-green font-bold text-sm text-center uppercase text-white tracking-widest-1 lg:w-36 w-44 lg:h-10 h-9"
                @click="Sendform()"
              >
                enviar
              </button>
            </div>
          </div>
        </form>
      </div>
    </div>
    <GoPremium2 class="lg:visible invisible lg:w-auto lg:h-auto w-0 h-0" />
    <Footer />
  </div>
</template>
  
  <style lang="scss" scoped>
.bg-gray {
  background: #e5e5e5;
}
.text-gray {
  color: #3c3c3b;
}
.text-dark-blue {
  color: #1c496b;
}
.border-blue-green {
  border: 1px solid #00a99d;
}
.bg-blue-green {
  background: #00a99d;
}
.text-blue-green {
  color: #00a99d;
}
.tracking-widest-1 {
  letter-spacing: 0.25em;
}
.w-90 {
  width: 328px;
}
.input-box {
  width: 535px;
  margin-right: -200px;
}
.message {
  min-height: 100px;
}
.return {
  background: url("~/static/img/icon/flecha_der_left.png") no-repeat 10% 50%;
}
.contact {
  background: none;
  ::-webkit-input-placeholder {
    color: transparent;
  }
  :-moz-placeholder {
    color: transparent;
  }
  ::-moz-placeholder {
    color: transparent;
  }
  :-ms-input-placeholder {
    color: transparent;
  }
  .hero-container {
    background: #557790;
    .hero {
      background: linear-gradient(163.41deg, #1c496b 0%, #00a99d 100%);
      transform: rotate(-180deg);
      .text {
        transform: rotate(-180deg);
      }
    }
  }
}
@media only screen and (max-width: 1023px) {
  .w-90 {
    width: auto;
  }
  .contact {
    background: url("~/static/img/background/Rectangle57-1.png") no-repeat;
    background-size: 100% 100%;
    ::-webkit-input-placeholder {
      text-align: center;
      color: #000;
    }
    :-moz-placeholder {
      text-align: center;
      color: #000;
    }
    ::-moz-placeholder {
      text-align: center;
      color: #000;
    }
    :-ms-input-placeholder {
      text-align: center;
      color: #000;
    }
    .hero-container {
      background: none;
      .hero {
        background: none;
        transform: rotate(-180deg);
        .text {
          transform: rotate(-180deg);
        }
      }
    }
  }
  .input-text {
    width: 100%;
  }
  .input-box {
    width: 100%;
    margin-right: 0;
  }
  .message {
    min-height: 200px;
  }
}
</style>