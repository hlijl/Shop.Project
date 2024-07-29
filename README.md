### React + TypeScript + Vite

Этот шаблон предоставляет минимальную настройку для работы с React в Vite, включая HMR (Hot Module Replacement) и некоторые правила ESLint.

В настоящее время доступны два официальных плагина:

- **@vitejs/plugin-react** использует Babel для Fast Refresh.
- **@vitejs/plugin-react-swc** использует SWC для Fast Refresh.

### Расширение конфигурации ESLint

Если вы разрабатываете приложение для продакшена, рекомендуется обновить конфигурацию, чтобы включить правила линтинга с учетом типов:

1. **Настройте свойство `parserOptions` на верхнем уровне следующим образом:**
   ```json
   parserOptions: {
     ecmaVersion: 'latest',
     sourceType: 'module',
     project: ['./tsconfig.json', './tsconfig.node.json'],
     tsconfigRootDir: __dirname,
   }
   ```

2. **Замените `plugin:@typescript-eslint/recommended` на `plugin:@typescript-eslint/recommended-type-checked` или `plugin:@typescript-eslint/strict-type-checked`.**

3. **Дополнительно можно добавить `plugin:@typescript-eslint/stylistic-type-checked`.**

4. **Установите `eslint-plugin-react` и добавьте `plugin:react/recommended` и `plugin:react/jsx-runtime` в список `extends`.**

Этот подход обеспечит более строгую и точную проверку вашего кода, улучшая его качество и стабильность.
