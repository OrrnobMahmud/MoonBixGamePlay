Check Out [Video Tutorial](https://t.me/verifiedcryptoairdops/197)


1. Copy The Following Code
2. Sign Up/Open [MoonBix Bot](https://t.me/Binance_Moonbix_bot/start?startApp=ref_1242349721&startapp=ref_1242349721&utm_medium=web_share_copy)
3. Click F12/Right Mouse to go it Inspection Mode.
4. Go to Console and Paste the following code.


```javascript
class MoonbixBot {
  sleep(time) {
    return new Promise((resolve) => setTimeout(resolve, time));
  }

  run() {
    setInterval(async () => {
      const buttonPlayGame = this.findButtonPlayGame();
      if (!buttonPlayGame) {
        return;
      }

      const event = new MouseEvent("click", {
        bubbles: true,
        cancelable: true,
        view: window,
      });
      buttonPlayGame.dispatchEvent(event);

      await this.sleep(1000);

      for (let i = 0; i < 50; i++) {
        await this.sleep(1000);
        this.simulateLeftClick();
      }

      this.findReturnButtonElementsAndClick();

      await this.sleep(1500);
    }, 1000);
  }

  findButtonPlayGame() {
    const button = document.querySelector("[class^='Game_entry__playBtn']");
    // if (button && button.textContent.trim().toLowerCase() === "chơi game") {
    if (button) {
      const style = window.getComputedStyle(button);
      if (style.marginTop === "40px") {
        return button;
      }
    }
    return null;
  }

  findReturnButtonElementsAndClick() {
    const svgs = document.getElementsByTagName("svg");
    for (let svg of svgs) {
      // Check if the SVG matches the specified structure
      if (
        svg.outerHTML ===
        '<svg class="bn-svg absolute top-4 start-4 w-6 h-6" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" clip-rule="evenodd" d="M2.999 11.999l7.071-7.072 1.768 1.768-4.055 4.055H21v2.5H7.785l4.053 4.053-1.768 1.768L3 12v-.001z" fill="currentColor"></path></svg>'
      ) {
        const event = new MouseEvent("click", {
          bubbles: true,
          cancelable: true,
          view: window,
        });
        svg.dispatchEvent(event);
      }
    }
  }

  autoMining() {}

  simulateLeftClick() {
    const canvas = document.querySelector("canvas");
    console.error("Canvas: ", canvas);
    if (canvas) {
      const event = new MouseEvent("mousedown", {
        bubbles: true,
        cancelable: true,
        view: window,
        button: 0, // 0 indicates the left mouse button
      });
      canvas.dispatchEvent(event);

      const clickEvent = new MouseEvent("mouseup", {
        bubbles: true,
        cancelable: true,
        view: window,
        button: 0, // 0 indicates the left mouse button
      });
      canvas.dispatchEvent(clickEvent);

      canvas.dispatchEvent(
        new MouseEvent("click", {
          bubbles: true,
          cancelable: true,
          view: window,
          button: 0, // 0 indicates the left mouse button
        })
      );
    }
  }
}

const moonBixBot = new MoonbixBot();
moonBixBot.run();

