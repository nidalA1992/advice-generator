<template>
  <svg height="16" xmlns="http://www.w3.org/2000/svg">
    <g fill="none" fill-rule="evenodd">
      <path id="mob" fill="#4F5D74" d="M0 8h122v1H0zM173 8h122v1H173z" />
      <path id="desc" fill="#4F5D74" d="M0 8h196v1H0zM248 8h196v1H248z" />
      <g fill="#CEE3E9">
        <rect width="6" height="16" rx="3" />
        <rect x="14" width="6" height="16" rx="3" />
      </g>
    </g>
  </svg>
</template>

<style scoped lang="scss">
svg {
  width: 295px;
  g g {
    transform: translate(138px);
  }
}
#desc {
  display: none;
}

@media (min-width: 768px) {
  #desc {
    display: inline;
  }
  #mob {
    display: none;
  }
  svg {
    width: 444px;
    g g {
      transform: translate(212px);
    }
  }
}
</style>
