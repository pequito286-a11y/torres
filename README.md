<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pequito - Sistema de Cuadre Completo</title>
    <style>
        :root {
            --primary: #1e40af;
            --primary-light: #3b82f6;
            --bg-light: #f1f5f9;
            --card-bg: #ffffff;
            --text-dark: #0f172a;
            --brand-tag-bg: #e2e8f0;
            --brand-tag-text: #475569;
        }

        * { box-sizing: border-box; font-family: 'Segoe UI', -apple-system, BlinkMacSystemFont, sans-serif; }

        body { background-color: var(--bg-light); margin: 0; padding: 10px; color: var(--text-dark); padding-bottom: 160px; }

        .header { text-align: center; background: var(--primary); color: white; padding: 15px; border-radius: 12px; margin-bottom: 12px; }
        .header h2 { margin: 0; font-size: 1.3rem; letter-spacing: 0.5px; }
        .header p { margin: 5px 0 0 0; font-size: 0.85rem; opacity: 0.9; }

        .vendedor-info { background: white; padding: 12px; border-radius: 12px; margin-bottom: 12px; display: flex; flex-direction: column; gap: 8px; box-shadow: 0 1px 3px rgba(0,0,0,0.05); }
        .vendedor-info .row { display: flex; gap: 8px; }
        .vendedor-info input { width: 100%; padding: 10px; border: 1px solid #cbd5e1; border-radius: 6px; font-size: 0.9rem; }
        .vendedor-info #cliente_name { border: 2px solid var(--primary); font-weight: bold; font-size: 0.95rem; }

        .search-container { position: sticky; top: 0; background: var(--bg-light); padding: 5px 0 10px 0; z-index: 100; }
        .search-bar { width: 100%; padding: 12px; border: 2px solid #64748b; border-radius: 8px; font-size: 1rem; font-weight: bold; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.05); }

        .products-container { display: flex; flex-direction: column; gap: 10px; }
        
        .product-card { background: var(--card-bg); border-radius: 12px; padding: 12px; box-shadow: 0 1px 3px rgba(0,0,0,0.05); border-left: 5px solid var(--primary-light); display: flex; flex-direction: column; gap: 8px; position: relative; }
        .product-card.hidden { display: none !important; }
        
        .product-meta { display: flex; justify-content: space-between; align-items: center; }
        .product-name { font-weight: 600; font-size: 0.95rem; color: #1e293b; max-width: 75%; }
        .product-brand { font-size: 0.7rem; font-weight: bold; background: var(--brand-tag-bg); color: var(--brand-tag-text); padding: 2px 6px; border-radius: 4px; text-transform: uppercase; }

        .inputs-row { display: flex; justify-content: space-between; gap: 8px; }
        .input-box { flex: 1; display: flex; flex-direction: column; align-items: center; background: #f8fafc; padding: 4px; border-radius: 6px; border: 1px solid #e2e8f0; }
        .input-box label { font-size: 0.65rem; font-weight: bold; color: #64748b; margin-bottom: 2px; }
        .input-box input { width: 100%; border: 1px solid #cbd5e1; border-radius: 4px; padding: 6px; text-align: center; font-size: 0.95rem; font-weight: bold; color: var(--primary); }

        /* Colores distintivos en el borde izquierdo por Marca para guiar al vendedor */
        .product-card[data-brand="GUSTOZZI"] { border-left-color: #e11d48; }
        .product-card[data-brand="SUPER CROOS"] { border-left-color: #ea580c; }
        .product-card[data-brand="BUCKYS"] { border-left-color: #16a34a; }
        .product-card[data-brand="ARTESANAL"] { border-left-color: #4f46e5; }
        .product-card[data-brand="PANKY"] { border-left-color: #db2777; }
        .product-card[data-brand="POWER DIET"] { border-left-color: #06b6d4; }
        .product-card[data-brand="FRUTO VERDE"] { border-left-color: #84cc16; }

        .footer-container { position: fixed; bottom: 0; left: 0; width…
