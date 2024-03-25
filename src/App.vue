<template>
  <section>
    <header>
      {{
        $formatMessage({
          defaultMessage: 'Control Panel',
          description: 'title of control panel section',
        })
      }}
    </header>
    <ul>
      <li>
        <button>
          {{
            $formatMessage(
              {
                defaultMessage: 'Delete user {name}',
                description: 'Delete button',
              },
              {
                name: props.name,
              }
            )
          }}
        </button>
      </li>
      <li>
        <input :placeholder="newPwdPlaceholder" />
        <input :placeholder="confirmPwdPlaceholder" />
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  inject: ['intl'],
  props: ['name'],
  data() {
    return {
      newPwdPlaceholder: $formatMessage({
        defaultMessage: 'New Password',
        description: 'placeholder text',
      }),
      confirmPwdPlaceholder: $formatMessage({
        id: 'explicit-id',
        defaultMessage: 'Confirm Password',
        description: 'placeholder text',
      }),
    }
  },
}
</script>
