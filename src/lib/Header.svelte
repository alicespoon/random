<a href="../" class="logo">
  <span class="accent-color">
    <span class="alice">alice</span> <span class="sp">sp</span><span class="o"
      >o</span
    ><span class="on">on.</span>
  </span>
</a>

<style>
  a {
    text-decoration: none;
    color: black;
  }

  .accent-color {
    color: #3e51ff;
  }

  .logo {
    display: block;
    padding: 8px 8px 12px 8px;

    font-family: degular-display, sans-serif;
    font-style: normal;
    font-weight: 400;
    font-size: 32px;
    line-height: 32px;

    color: inherit;
  }

  .logo:hover {
    background-color: #3e51ff;
  }

  .logo:hover span {
    color: white;
  }

  @media screen and (min-width: 480px) {
    .logo > span {
      display: grid;
      grid-template-columns: 12rem repeat(9, 1fr);
      column-gap: 8px;
    }

    .alice {
      grid-column: 1 / 3;
    }
    .sp {
      grid-column: 3 / 7;
    }
    .o {
      grid-column: 7 / 9;
    }
    .on {
      grid-column: 9 / 11;
      text-align: right;
    }
  }
</style>
