async function unblur() {
  console.log("unblur");
  const teasers = await fetch(
    "https://api.gotinder.com/v2/fast-match/teasers",
    { headers: { "X-Auth-Token": localStorage.getItem("TinderWeb/APIToken") } }
  )
    .then((res) => res.json())
    .then((res) => res.data.results);
  const teaserEls = document.querySelectorAll(
    ".Expand.enterAnimationContainer > div:nth-child(1)"
  );

  for (let i = 0; i < teaserEls.length; ++i) {
    const teaser = teasers[i];
    const teaserEl = teaserEls[i];
    console.log(teaser);

    const teaserImage = teaser.user.photos[0].url;

    teaserEl.style.backgroundImage = `url(${teaserImage})`;
  }
}

var is_blurry = true;
setInterval(() => {
  if (
    is_blurry &&
    ["/app/likes-you", "/app/gold-home"].includes(location.pathname)
  ) {
    unblur();
    is_blurry = false;
  }
}, 5000);
