# Tổng quan dự án
Dự án được xây dựng với mục tiêu tự động hóa việc kiểm soát và bảo vệ khu vực để xe tại các hộ gia đình, nhà trọ, hoặc khu dân cư nhỏ, bằng cách ứng dụng Trí tuệ nhân tạo (AI) kết hợp với các thiết bị phần cứng chi phí thấp.

Hệ thống sử dụng Raspberry Pi 4 làm trung tâm điều khiển, kết nối với nhiều thiết bị như camera, vi điều khiển Arduino, cảm biến, đèn và động cơ. Ba chức năng AI chính bao gồm:

✅ 1. Nhận diện khuôn mặt – Mở cửa tự động
Sử dụng thư viện face_recognition với mô hình backbone ResNet-34 để trích xuất embedding khuôn mặt và so sánh.

Để đảm bảo độ chính xác cao, người dùng hợp lệ cần cung cấp từ 5–10 ảnh khuôn mặt trong điều kiện ánh sáng tốt và rõ nét.

Khi camera nhận diện được người hợp lệ, hệ thống sẽ kích hoạt cơ cấu mở cửa tự động thông qua servo hoặc motor bước.

✅ 2. Phát hiện người – Cảnh báo xâm nhập
Áp dụng mô hình YOLOv8n, đã được fine-tune lại trên dữ liệu thực tế thu thập tại khu vực để xe với điều kiện ánh sáng yếu (ban đêm, thiếu sáng…).

Ảnh được tự thu thập thủ công từ camera giám sát, sau đó được gán nhãn (labeling) bằng công cụ Roboflow để chuẩn bị cho quá trình huấn luyện lại mô hình.

Khi phát hiện có người di chuyển bất thường trong khu vực ngoài giờ cho phép, hệ thống sẽ gửi cảnh báo và có thể ghi lại video/tắt mở đèn cảnh báo.

✅ 3. Nhận diện giọng nói – Điều khiển thiết bị
Hệ thống hỗ trợ điều khiển bằng giọng nói thông qua mô hình nhận dạng tiếng nói offline VOSK, sử dụng gói tiếng Việt có sẵn.

Người dùng có thể ra lệnh bằng tiếng Việt để bật/tắt đèn, cửa, còi báo, hoặc thực hiện các tác vụ cơ bản mà không cần dùng tay.


# Client:
## React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default tseslint.config({
  extends: [
    // Remove ...tseslint.configs.recommended and replace with this
    ...tseslint.configs.recommendedTypeChecked,
    // Alternatively, use this for stricter rules
    ...tseslint.configs.strictTypeChecked,
    // Optionally, add this for stylistic rules
    ...tseslint.configs.stylisticTypeChecked,
  ],
  languageOptions: {
    // other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default tseslint.config({
  plugins: {
    // Add the react-x and react-dom plugins
    'react-x': reactX,
    'react-dom': reactDom,
  },
  rules: {
    // other rules...
    // Enable its recommended typescript rules
    ...reactX.configs['recommended-typescript'].rules,
    ...reactDom.configs.recommended.rules,
  },
})
```

# Server:
## Set up back-end

b1: cd ../pbl5/be

b2: python -m venv .venv

b3: .venv\Scripts\Activate.ps1

b4: python -m pip install --upgrade pip

b5: pip install -r requirements.txt

## run server

fastapi dev main.py
