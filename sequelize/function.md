好的,我为你整理了 Sequelize 中所有主要方法及其参数、功能和使用示例。这些方法涵盖了 Sequelize 的核心 CRUD 操作以及其他常见的操作,希望对你的学习有所帮助。

1. 连接和定义模型

- `new Sequelize(database, [username], [password], [options])` 
  - 功能: 创建一个新的 Sequelize 实例,连接到指定的数据库
  - 参数:
    - `database`: 数据库名称
    - `username`: 数据库用户名(可选)
    - `password`: 数据库密码(可选)
    - `options`: 连接选项对象(可选)
      - `host`: 数据库主机地址(默认: 'localhost')
      - `port`: 数据库端口号(默认: 3306)
      - `dialect`: 数据库类型(默认: 'mysql')
      - `logging`: 是否启用日志记录(默认: false)
      - `timestamps`: 是否启用时间戳(默认: true)
      - `paranoid`: 是否启用软删除(默认: false)
      - `createdAt`: 创建时间字段名称(默认: 'created_at')
      - `updatedAt`: 更新时间字段名称(默认: 'updated_at')
  - 示例:
    ``` sql
    const sequelize = new Sequelize('database_name', 'username', 'password', {
      host: 'localhost',
      dialect: 'mysql',
      logging: false
    });
    ```

- `sequelize.define(modelName, attributes, [options])`
  - 功能: 定义一个新的数据模型
  - 参数: 
    - `modelName`: 模型名称
    - `attributes`: 模型属性定义对象
    - `options`: 模型配置选项(可选)
      - timestamps: 是否启用时间戳(默认: true)
      - paranoid: 是否启用软删除(默认: false)
      - createdAt: 创建时间字段名称(默认: 'created_at')
      - updatedAt: 更新时间字段名称(默认: 'updated_at')
      - indexes: 索引定义数组(可选)
      - unique: 是否启用唯一索引(默认: false)
      - fields: 索引字段数组(可选)
   
  - 示例:
    ``` sql
    const User = sequelize.define('User', {
      name: DataTypes.STRING,
      email: DataTypes.STRING
    });
    ```

1. CRUD 操作

- `Model.create(values, [options])`
  - 功能: 创建并保存一个新的数据实例
  - 参数:
    - `values`: 要创建的数据对象
    - `options`: 创建选项(可选)
  - 示例:
    ``` sql
    const user = await User.create({ name: 'John Doe', email: 'john@example.com' });
    ```
- `Model.bulkCreate(valuesArray, [options])`
  - 功能: 批量创建并保存多个数据实例
  - 参数:
    - `valuesArray`: 要创建的数据对象数组
    - `options`: 创建选项(可选)
      - repeatable: 是否允许重复的值(默认: false)
      - returning: 是否返回创建的数据实例(默认: true)
      - individualHooks: 是否为每个数据实例执行钩子函数(默认: false)
      - validate: 是否验证数据实例(默认: true)
      - ignoreDuplicates: 是否忽略重复的数据实例(默认: false)
      - logging: 是否启用日志记录(默认: false)
  - 示例:
  - 示例:
  - 示例:
    ``` sql
    const users = await User.bulkCreate([
      { name: 'John Doe', email: 'john@example.com' },
      { name: 'Jane Smith', email: 'jane@example.com' }
    ]);
    ```
- `Model.findAndCountAll([options])`
  - 功能:
    - 查找符合条件的所有数据实例
    - 并返回一个包含数据实例数组和总记录数的对象
  - 参数:
    - `options`: 查找选项(可选)
  - 示例:
    ``` sql
    const users = await User.findAndCountAll({
      where: { name: 'John Doe' }
    });
    ```
- `Model.findOneAndUpdate()`
  - 功能:
    - 查找符合条件的单个数据实例
    - 并更新该实例的属性值
    - 并返回更新后的数据实例
  - 参数:
    - `options`: 查找选项(可选)
  - 示例:
    ``` sql
    const user = await User.findOneAndUpdate({ where: { id: 1 } }, { name: 'John Doe' });
    ```
- `Model.findAll([options])`
  - 功能: 查找符合条件的所有数据实例
  - 参数:
- `Model.findByPk(id, [options])`
  - 功能: 根据主键 ID 查找单个数据实例，并返回该实例
  - 使用场景:
    - 当需要根据主键 ID 查找单个数据实例时使用
    - 用户是否存在，类别嵌套等
  - 参数:
    - `id`: 主键 ID 值
    - `options`: 查找选项(可选)
  - 示例:
    ``` sql
    const user = await User.findByPk(1);
    user.name = 'John Doe';
    await user.save();
    ```

- `Model.findOne([options])`
  - 功能: 查找符合条件的单个数据实例
  - 参数:
    - `options`: 查找选项(可选)
  - 示例:
    ``` sql
    const user = await User.findOne({ where: { email: 'john@example.com' } });
    ```
- `Model.findOrCreate([options], [defaults])`
  - 功能:
    - 查找符合条件的单个数据实例,如果不存在则创建一个新实例
    - 返回一个包含数据实例和是否创建的布尔值的对象
  - 参数:
    - `options`: 查找选项(可选)
    - `defaults`: 默认属性值对象(可选)
  - 示例:
    ``` sql
    const [user, created] = await User.findOrCreate({ 
        where: { email: 'john@example.com' },
        defaults: {
          name: 'John Doe',
          email: 'john@example.com'
        });
     if(created){
        //创建了新数据
     }else{
        //找到了已存在的数据
     }
    ```
- `Model.upsert([options])`
  - 功能:
    - 它首先查找满足指定条件的记录是否存在
    - 如果记录存在,则执行更新操作,更新指定的字段
    - 如果记录不存在,则执行插入操作,创建新的记录
  - 参数:
    - `options`: 查找选项(可选)
  - 示例:
    ``` sql
    const [user, created] = await User.upsert({ 
        name: 'John Doe',
        email: 'john@example.com' 
    });
    if(created){
       //创建了新数据
    }else{
       //更新已存在的数据
    }
    ```
- `Model.findAll([options])`
  - 功能: 查找符合条件的所有数据实例
  - 参数:
    - `options`: 查找选项(可选)
  - 示例:
    ``` sql
    const users = await User.findAll();
    const activeUsers = await User.findAll({ where: { active: true } });
    ```

- `instance.save([options])`
  - 功能: 保存对数据实例的修改
  - 参数:
    - `options`: 保存选项(可选)
  - 示例:
    ``` sql
    const user = await User.findByPk(1);
    user.name = 'Jane Doe';
    await user.save();
    ```

- `instance.update(values, [options])`
  - 功能:
    - 更新数据实例的属性值
    - 并返回更新后的数据实例
  - 参数:
    - `values`: 属性值对象
    - `options`: 更新选项(可选)
  - 示例:
    ``` sql
    await user.update({ name: 'Jane Doe' },{where: {id: 1}});
    ```

- `instance.destroy([options])`
  - 功能: 删除数据实例
  - 参数:
    - `options`: 删除选项(可选)
  - 示例:
    ``` sql
    const user = await User.findByPk(1);
    await user.destroy();
    ```

- `sequelize.max([options])`
  - 功能: 获取指定字段的最大值
  - 参数:
    - `options`: 查找选项(可选)
  - 示例:
    ``` sql
    const maxAge = await User.max('age');
    ```

- `sequelize.min([options])`
  - 功能: 获取指定字段的最小值
  - 参数:
    - `options`: 查找选项(可选)
  - 示例:
    ``` sql
      const minAge = await User.min('age');
      ```

- `sequelize.sum([options])`
  - 功能: 获取指定字段的求和值
  - 参数:
    - `options`: 查找选项(可选)
  - 示例:
    ``` sql
      const totalAge = await User.sum('age');
      ```

- `sequelize.count([options])`
  - 功能: 获取满足指定条件的数据实例数量
  - 参数:
    - `options`: 查找选项(可选)
  - 示例:
    ``` sql
      const count = await User.count({ where: { active: true } });
      ```

- `sequelize.findByPkOrFail(id, [options])`
  - 功能: 根据主键查找数据实例，如果不存在则抛出错误
  - 参数:
    - `id`: 主键值
    - `options`: 查找选项(可选)
  - 示例:
    ``` sql
      const user = await User.findByPkOrFail(1);
      ```