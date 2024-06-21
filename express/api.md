Express.js 中 `express-validator` 库提供了一些常用的 API,以下是一些主要的 API:

1. **校验规则函数**:
   - `body(field)`: 验证 `req.body` 中的字段。
   - `param(field)`: 验证 `req.params` 中的字段。
   - `query(field)`: 验证 `req.query` 中的字段。
   - `header(field)`: 验证 `req.headers` 中的字段。

2. **校验规则方法**:
   - `notEmpty()`: 检查字段是否非空。
   - `isEmail()`: 检查字段是否为有效的电子邮件地址。
   - `isURL()`: 检查字段是否为有效的 URL。
   - `isInt()`: 检查字段是否为整数。
   - `isFloat()`: 检查字段是否为浮点数。
   - `isLength({ min, max })`: 检查字段长度是否在指定范围内。
   - `matches(regex)`: 检查字段是否匹配指定的正则表达式。
   - `custom(validator)`: 使用自定义验证函数进行校验。

3. **错误处理**:
   - `validationResult(req)`: 获取请求的验证结果。
   - `Result.isEmpty()`: 检查是否存在验证错误。
   - `Result.array()`: 获取所有验证错误。
   - `Result.mapped()`: 获取错误信息的映射对象。

4. **中间件**:
   - `check(field, message)`: 创建一个验证中间件。
   - `checkSchema(schema)`: 使用校验规则对象创建验证中间件。
   - `oneOf(validators)`: 检查至少有一个字段通过验证。
   - `not().exists()`: 检查字段不存在。

5. **自定义验证**:
   - `withMessage(message)`: 设置验证失败时的错误消息。
   - `bail()`: 当前验证失败后停止后续验证。
   - `custom(validator)`: 使用自定义验证函数进行校验。
   - `exists()`: 检查字段是否存在。
