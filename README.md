# 🔒 Vulnerabilidad: Falta de cabecera Anti-Clickjacking (`X-Frame-Options` / `CSP`)

- **Dominio afectado**: [https://www.aptosnames.com](https://www.aptosnames.com)
- **Fecha del hallazgo**: 18/04/2025
- **Herramienta utilizada**: OWASP ZAP 2.16.1
- **Tipo de vulnerabilidad**: Clickjacking
- **Riesgo**: Medio
- **CWE ID**: [CWE-1021](https://cwe.mitre.org/data/definitions/1021.html)
- **WASC ID**: 15

## 🧪 Descripción

El sitio web no presenta cabeceras de protección contra ataques de tipo **Clickjacking**, permitiendo ser cargado en un `iframe` y manipulado visualmente para engañar al usuario.

## ✅ Prueba de Concepto (PoC)

Se encuentra en el directorio `/PoC/poc.html`. Abrir localmente en el navegador.

## 🧩 Solución recomendada

Incluir una de las siguientes cabeceras HTTP:

### Opción 1: X-Frame-Options

```
X-Frame-Options: DENY
```

### Opción 2: Content Security Policy

```
Content-Security-Policy: frame-ancestors 'none';
```

## 📊 CVSS 3.1 – Score

**Vector:** `CVSS:3.1/AV:N/AC:L/PR:N/UI:R/S:U/C:L/I:L/A:N`  
**Base Score:** 5.4 (Medium)

## 📚 Referencias

- [OWASP Clickjacking Defense Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Clickjacking_Defense_Cheat_Sheet.html)
- [MDN - X-Frame-Options](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options)
