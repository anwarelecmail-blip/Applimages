const generateBtn = document.getElementById('generateBtn');
const promptInput = document.getElementById('prompt');
const widthSelect = document.getElementById('width');
const heightSelect = document.getElementById('height');
const enhanceCheckbox = document.getElementById('enhance');
const statusDiv = document.getElementById('status');
const resultDiv = document.getElementById('result');
const generatedImage = document.getElementById('generatedImage');
const downloadLink = document.getElementById('downloadLink');

generateBtn.addEventListener('click', async () => {
  const prompt = promptInput.value.trim();

  if (!prompt) {
    statusDiv.textContent = '⚠️ Écris d\'abord un prompt.';
    return;
  }

  // Réinitialiser
  resultDiv.classList.add('hidden');
  statusDiv.textContent = '⏳ Génération en cours... (cela peut prendre 10-20 secondes)';
  generateBtn.disabled = true;

  try {
    const width = widthSelect.value;
    const height = heightSelect.value;
    const enhance = enhanceCheckbox.checked;

    // Construction de l'URL Pollinations
    const encodedPrompt = encodeURIComponent(prompt);
    const url = `https://image.pollinations.ai/prompt/${encodedPrompt}?width=${width}&height=${height}&enhance=${enhance}&nologo=true&seed=${Date.now()}`;

    // Charger l'image
    const img = new Image();
    img.crossOrigin = 'anonymous';

    img.onload = () => {
      generatedImage.src = url;
      downloadLink.href = url;
      downloadLink.download = `image-ia-${Date.now()}.jpg`;
      resultDiv.classList.remove('hidden');
      statusDiv.textContent = '✅ Image générée !';
      generateBtn.disabled = false;
    };

    img.onerror = () => {
      statusDiv.textContent = '❌ Erreur lors de la génération. Réessaie avec un autre prompt.';
      generateBtn.disabled = false;
    };

    img.src = url;

  } catch (error) {
    statusDiv.textContent = '❌ Erreur : ' + error.message;
    generateBtn.disabled = false;
  }
});
