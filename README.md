# Phone-AR

A lightweight mobile-first web experience that lets you point your phone camera, load a ManualLabs document, and highlight the exact part you need to inspect. Built with Three.js and WebXR, it falls back to a camera-only preview when AR is unavailable.

## Getting started

1. Serve the folder over HTTPS (required by WebXR/camera APIs) using any static server. For example:
   ```bash
   npx http-server -S -C cert.pem -K key.pem -p 8080
   ```
   Or use your preferred hosting (Firebase Hosting, Vercel, GitHub Pages with HTTPS, etc.).
2. Open the served URL on your phone (Chrome Android or Safari iOS).
3. Grant camera + motion permissions when prompted.
4. Pick a ManualLabs document and part from the dropdowns, then tap **Start AR session**.
5. Move your phone to view the 3D overlay and orange highlight for the selected part.

## Features

- **Two sample ManualLabs documents** with glTF models loaded from the Khronos sample set.
- **Part-level highlighting**: every part in the dropdown moves the orange highlight sphere to its coordinates.
- **WebXR AR mode** with dom-overlay controls; **camera preview fallback** when XR is not supported.
- Responsive, phone-friendly UI with clear status guidance for technicians.

## Notes

- WebXR requires HTTPS and device support. The fallback still provides a live camera feed and part labels.
- Model URLs can be swapped to point at real ManualLabs assets without code changes.
