<template>
    <button :class="`alli-button ${size} ${variationClass} ${shadowClass}`" :disabled="disabled">
        <slot></slot>
    </button>
</template>

<script>
  export default {
    props: {
      disabled: {
        type: Boolean,
        default: false,
        required: false
      },
      size: {
        type: String,
        default: "md",
        required: false
      },
      variation: {
        type: String,
        default: "primary",
        required: false
      },
      outline: {
        type: Boolean,
        default: false,
        required: false
      },
      shadow:{
        type: String,
        default: "",
        required: false
      }
    },
    computed: {
      variationClass() {
        //return this.outline ? `${this.variation}-outline` : `${this.variation}`

        if (this.outline) {
          return `${this.variation}-outline`;
        }
        return this.variation;
      },
      shadowClass(){
        if(!this.shadow){
          return "";
        }
        return `shadow-${this.shadow}`
      }
    }
  };
</script>
<style lang="scss" scoped>
    $primary : #3d5af1;
    $secondary : #f3558e;
    $danger : #85203b;
    $success : #17b978;

    .alli-button {
        font-size     : 1rem;
        border-radius : 0.25rem;
        padding       : 0.5rem 0.8rem;
        cursor        : pointer;

        &.primary {
            background-color : $primary;
            color            : #ffffff;
            &-outline {
                background-color : transparent;
                color            : $primary;
                border-color     : $primary;
                &:hover {
                    color : #ffffff;
                }
            }
        }

        &.secondary {
            background-color : $secondary;
            color            : #ffffff;
            &:hover {
                background-color : darken($secondary, 5%);

            }
            &-outline {
                background-color : transparent;
                color            : $secondary;
                border-color     : $secondary;
                &:hover {
                    color : #ffffff;
                    background-color: $secondary;
                }
            }
        }

        &.danger {
            background-color : $danger;
            color            : #ffffff;
            &:hover {
                background-color : darken($danger, 5%);

            }
            &-outline {
                background-color : transparent;
                color            : $danger;
                border-color     : $danger;
                &:hover {
                    color : #ffffff;
                    background-color : $danger;
                }
            }
        }

        &.success {
            background-color : $success;
            color            : #ffffff;
            &:hover {
                background-color : darken($success, 5%);

            }
            &-outline {
                background-color : transparent;
                color            : $success;
                border-color     : $success;
                &:hover {
                    color : #ffffff;
                    background-color: $success;
                }
            }
        }

        &.sm {
            font-size : 0.75rem;
        }
        &.lg {
            font-size : 1.25rem;
        }

        &:hover {
            background-color : darken($primary, 5%);
        }

        &:disabled {
            cursor           : not-allowed;
            background-color : darkgrey;

        }

        /*shadows*/

        &.shadow{
            &-sm{
                box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
            }
            &-md{
                box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);

            }
            &-lg{
                box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
            }
        }
    }
</style>