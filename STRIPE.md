# Conectar Stripe a Casa Amelí

Esta guía te lleva paso a paso para crear tus Payment Links de Stripe, configurarlos para que el cliente pueda escribir su mensaje en el pago, y enlazarlos a la web.

---

## 1. Crear cuenta en Stripe

1. Entra en https://stripe.com y regístrate.
2. Completa la activación de tu cuenta (te pedirán datos fiscales para cobrar).
3. Ve al **Dashboard**.

---

## 2. Crear los productos

En el Dashboard de Stripe ve a **Productos → + Añadir producto**. Crea estos 4:

### Producto 1: Pack Básico
- **Nombre:** Pack Básico — Casa Amelí
- **Descripción:** Pulsera cargador + 1 bolsita a elegir.
- **Precio:** 14,99 € (de tipo "Una sola vez")
- Guarda.

### Producto 2: Regalo Personalizado
- **Nombre:** Regalo Personalizado — Casa Amelí
- **Descripción:** Pulsera cargador + bolsita a elegir + tarjeta personalizada con tipografía a elegir.
- **Precio:** 17,99 €
- Guarda.

### Producto 3: Pack 2 Básico
- **Nombre:** Pack 2 Básico — Casa Amelí
- **Descripción:** 2 pulseras cargador + 2 bolsitas a elegir.
- **Precio:** 24,99 €
- Guarda.

### Producto 4: Pack Dúo Personalizado
- **Nombre:** Pack Dúo Personalizado — Casa Amelí
- **Descripción:** 2 pulseras cargador + 2 bolsitas a elegir + hasta 2 tarjetas personalizadas.
- **Precio:** 29,99 €
- Guarda.

---

## 3. Crear los Payment Links

Ve a **Pagos → Payment Links → + Nuevo**. Crea uno para cada producto.

### Para los packs **NO personalizados** (Básico y Pack 2 Básico)

1. Selecciona el producto.
2. En **Opciones**, activa:
   - ✅ **Solicitar dirección de envío** (España)
   - ✅ **Recopilar número de teléfono** (opcional, recomendado)
3. En **Campos personalizados** (Custom fields) añade:
   - **Campo "Bolsita":**
     - Tipo: `Desplegable` (Dropdown)
     - Etiqueta: `Color de la bolsita`
     - Opciones (Básico): `Natural`, `Negra`, `Sin preferencia`
     - Opciones (Pack 2): `2 naturales`, `2 negras`, `1 natural + 1 negra`, `Sin preferencia`
     - **Obligatorio:** sí
4. Guarda y **copia el enlace**. Te dará una URL tipo `https://buy.stripe.com/xxxxx`.

### Para los packs **personalizados** (Regalo Personalizado y Pack Dúo)

1. Selecciona el producto.
2. Activa lo mismo de arriba.
3. En **Campos personalizados** añade estos 3:

   **a) Mensaje de la tarjeta**
   - Tipo: `Texto`
   - Etiqueta: `Tu mensaje para la tarjeta (máx 80 caracteres)`
   - Texto de ayuda: `Ej: Para Laura, para que nunca te quedes sin batería 🤍`
   - Obligatorio: sí

   **b) Tipografía**
   - Tipo: `Desplegable`
   - Etiqueta: `Tipografía de la tarjeta`
   - Opciones: `París`, `Gala`, `Amour`, `Nota`, `Sonrisa`
   - Obligatorio: sí

   **c) Bolsita**
   - Tipo: `Desplegable`
   - Etiqueta: `Color de la bolsita`
   - Opciones (Personalizado): `Natural`, `Negra`, `Sin preferencia`
   - Opciones (Pack Dúo): `2 naturales`, `2 negras`, `1 natural + 1 negra`, `Sin preferencia`
   - Obligatorio: sí

   **Solo para Pack Dúo, añade un cuarto campo:**

   **d) Segundo mensaje (opcional)**
   - Tipo: `Texto`
   - Etiqueta: `Segundo mensaje (si quieres 2 tarjetas distintas)`
   - Obligatorio: no

4. Guarda y **copia el enlace**.

---

## 4. Pegar los enlaces en la web

Abre `index.html` con cualquier editor y haz **Buscar y reemplazar** (Ctrl+H):

| Busca esto | Sustituye por |
|---|---|
| `STRIPE_LINK_BASICO` | URL del Payment Link del Pack Básico |
| `STRIPE_LINK_PERSONALIZADO` | URL del Regalo Personalizado |
| `STRIPE_LINK_PACK_2_BASICO` | URL del Pack 2 Básico |
| `STRIPE_LINK_PACK_DUO` | URL del Pack Dúo |

Guarda y sube el cambio a GitHub. Vercel actualizará la web sola.

---

## 5. Probar antes de publicar

Stripe tiene un **modo de prueba**. En el Dashboard arriba a la derecha verás un interruptor `Test mode`. Crea Payment Links en modo prueba para verificar que todo funciona sin cobrar de verdad. Stripe tiene tarjetas de prueba aquí: https://docs.stripe.com/testing

Cuando lo veas bien, desactiva el modo prueba y crea los Payment Links definitivos.

---

## 6. ¿Y los pedidos? ¿Dónde los veo?

Cada vez que alguien pague, recibirás:
- Un **email de Stripe** con los datos del pedido y los campos personalizados (mensaje, tipografía, bolsita).
- Lo verás también en el **Dashboard → Pagos**.

Recomiendo activar la **app móvil de Stripe** para que te llegue notificación al móvil.

---

## 7. Costes de Stripe (orientativo)

Stripe cobra una comisión por transacción. En España, suele ser sobre **1,4% + 0,25 €** por pago con tarjeta europea. Confirma las tarifas actualizadas en https://stripe.com/es/pricing.

No hay cuota mensual ni alta. Solo pagas comisión por venta.

---

## 8. Dudas frecuentes

**¿Necesito crear empresa o autónomo para usar Stripe?**
Stripe te pedirá datos fiscales. En España normalmente necesitas estar dado de alta como autónomo o tener una sociedad. Consulta con un asesor.

**¿Stripe envía la factura al cliente?**
Sí, automáticamente le envía el recibo por email. Si quieres facturas legales con tus datos fiscales, configúralo en Stripe → Configuración → Facturación.

**¿Y si el cliente quiere cancelar?**
Puedes reembolsar el pago desde el Dashboard de Stripe con un clic.

---

¿Algo no te cuadra? Documentación oficial: https://docs.stripe.com/payment-links
