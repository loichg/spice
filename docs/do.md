# Create Your Custom Pack

Create your own pack of 10 SnapCaps by choosing from our wide range of flavors, rated from 1 to 5 points. Mix and match to suit your taste!

## How It Works

1. **Choose Your Capsules**:  
   Select up to 10 capsules from our extensive flavor range. Each capsule is rated from 1 to 5 points.

2. **Respect the Point Limit**:  
   Your pack must not exceed 10 points in total to ensure an affordable production cost.

3. **Confirm and Order**:  
   Once your pack is finalized, place your order and receive it at your doorstep within days.

## Available Flavors

| Flavor               | Points | Description                          |
|-----------------------|--------|--------------------------------------|
| Sea Salt             | 1      | Pure and natural, perfect for all dishes. |
| Black Pepper         | 1      | Spicy and aromatic.                 |
| Smoked Paprika       | 2      | Mild and slightly smoky.            |
| Turmeric             | 2      | Golden spice with health benefits.  |
| Cumin                | 3      | Warm and earthy, ideal for curries. |
| Espelette Pepper     | 4      | Spicy and fruity, from the Basque region. |
| Saffron              | 5      | The rarest and most precious spice. |

## Create Your Pack

```html
<form action="https://formspree.io/f/your-form-id" method="POST">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name" required>

  <label for="email">Email Address:</label>
  <input type="email" id="email" name="email" required>

  <label for="capsules">Select Your Capsules:</label>
  <select id="capsules" name="capsules" multiple required>
    <option value="sea_salt" data-points="1">Sea Salt (1 point)</option>
    <option value="black_pepper" data-points="1">Black Pepper (1 point)</option>
    <option value="smoked_paprika" data-points="2">Smoked Paprika (2 points)</option>
    <option value="turmeric" data-points="2">Turmeric (2 points)</option>
    <option value="cumin" data-points="3">Cumin (3 points)</option>
    <option value="espelette_pepper" data-points="4">Espelette Pepper (4 points)</option>
    <option value="saffron" data-points="5">Saffron (5 points)</option>
  </select>

  <p>Total Points: <span id="total-points">0</span>/10</p>

  <button type="submit" id="submit-button" disabled>Order Now</button>
</form>

<script>
  const select = document.getElementById('capsules');
  const totalPointsDisplay = document.getElementById('total-points');
  const submitButton = document.getElementById('submit-button');

  let totalPoints = 0;

  select.addEventListener('change', (event) => {
    totalPoints = Array.from(event.target.selectedOptions)
      .reduce((sum, option) => sum + parseInt(option.dataset.points), 0);
    totalPointsDisplay.textContent = totalPoints;

    if (totalPoints <= 10) {
      submitButton.disabled = false;
    } else {
      submitButton.disabled = true;
    }
  });
</script>