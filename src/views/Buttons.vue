<template>

    <div class="buttons">
        <h1>This is a buttons page</h1>
        <alli-button>alli-button-default</alli-button>
        <alli-button :disabled="true">alli-button-disabled</alli-button>
        <doc-section title="Button Sizes">
            <div>
                <alli-button size="sm">alli-button-small</alli-button>
            </div>
            <div>
                <alli-button size="md">alli-button-medium</alli-button>
            </div>
            <div>
                <alli-button size="lg">alli-button-large</alli-button>
            </div>
        </doc-section>
        <doc-section title="Color Variations">
            <alli-button variation="secondary">alli-button-secondary</alli-button>
            <alli-button variation="danger">alli-button-danger</alli-button>
            <alli-button variation="success">alli-button-success</alli-button>
        </doc-section>
        <doc-section title="Outline Colors">
            <alli-button :outline="true" variation="primary">alli-button-primary-outline</alli-button>
            <alli-button :outline="true" variation="secondary">alli-button-secondary-outline</alli-button>
            <alli-button :outline="true" variation="danger">alli-button-danger-outline</alli-button>
            <alli-button :outline="true" variation="success">alli-button-success-outline</alli-button>
        </doc-section>
        <doc-section title="Button Shadows">
            <alli-button shadow="sm" variation="primary">alli-button-primary-outline</alli-button>
            <alli-button shadow="md" variation="primary">alli-button-primary-outline</alli-button>
            <alli-button shadow="lg" variation="primary">alli-button-primary-outline</alli-button>

        </doc-section>
    </div>
</template>

<script>
  import AlliButton from "../components/Atoms/Buttons/AlliButton/AlliButton";
  import DocSection from "../components/DocSection";

  export default {
    components: {
      "alli-button": AlliButton,
      "doc-section": DocSection
    }
  };
</script>
