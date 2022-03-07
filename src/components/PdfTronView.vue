<template>
  <div class="pdftron" ref="viewer" />
</template>

<script>
import WebViewer from "@pdftron/webviewer";
export default {
  mounted() {
    this.$nextTick(() => {
      // eslint-disable-next-line
      const p = WebViewer(
        {
          path: `${process.env.BASE_URL}webviewer`,
          licenseKey: 'testing_key',
          initialDoc: "/pdf/sample.pdf",
        },
        this.$refs.viewer
      )
        .then((instance) => {
          console.log("LOADED", instance);
        })
        .catch((err) => {
          console.error("Err", err);
        })
        .finally(() => {
          console.log("Finished");
        });
      console.log('Promise:', p);
    });
  },
};
</script>

<style scoped>
.pdftron {
  width: 100vw;
  height: 40vh;
}
</style>
