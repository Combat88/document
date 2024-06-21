
1. `include`
   - 功能: 查询时包含关联模型的数据
   - 示例:
     ```javascript
     const posts = await Post.findAll({
       include: [
         { model: User, as: 'author' },
         { model: Comment, include: [User] }
       ]
     });
     ```
   - SQL 语句: `SELECT * FROM "Posts" LEFT JOIN "Users" AS "author" ON "Posts"."authorId" = "author"."id" LEFT JOIN "Comments" ON "Posts"."id" = "Comments"."postId" LEFT JOIN "Users" ON "Comments"."userId" = "Users"."id"`

2. `attributes`
   - 功能: 指定查询返回的字段
   - 示例:
     ```javascript
     const users = await User.findAll({
       attributes: ['id', 'name', 'email']
     });
     const userNames = await User.findAll({
       attributes: ['name']
     });
     const users = await User.findAll({
       attributes: { exclude: ['createdAt', 'updatedAt'] }
     });
     const users = await User.findAll({
       attributes: ['id', 'name', 'profile.bio'],
       include: [{ model: Profile, as: 'profile' }]
     });
     ```
   - SQL 语句: `SELECT "id", "name", "email" FROM "Users"` / `SELECT "name" FROM "Users"` / `SELECT "id", "name", "profile"."bio" FROM "Users" LEFT JOIN "Profiles" AS "profile" ON "Users"."id" = "profile"."userId"`

3. `group` 和 `having`
   - 功能: 对查询结果进行分组,并应用 HAVING 过滤条件
   - 示例:
     ```javascript
     const userCounts = await User.findAll({
       attributes: ['status', [Sequelize.fn('COUNT', Sequelize.col('id')), 'count']],
       group: ['status'],
       having: {
         count: {
           [Op.gt]: 1
         }
       }
     });
     ```
   - SQL 语句: `SELECT "status", COUNT("id") AS "count" FROM "Users" GROUP BY "status" HAVING "count" > 1`

4. `raw`
   - 功能: 返回原始查询结果,而不是 Sequelize 模型实例
   - 示例:
     ```javascript
     const users = await User.findAll({
       raw: true
     });
     ```
   - SQL 语句: `SELECT * FROM "Users"`

5. `subQuery`
   - 功能: 设置为 true 时,将使用子查询来执行查询,设置为 false 时,将使用主查询来执行查询
   - 示例:
     ```javascript
     const users = await User.findAll({
       where: {
         id: {
           [Op.in]: Sequelize.literal('SELECT id FROM posts WHERE status = \'active\'')
         }
       },
       subQuery: false
     });
     ```
   - SQL 语句: 
     - 子查询: 
     - 主查询:

6. `paranoid`
   - 功能: 设置为 true 时,将使用软删除来删除记录
   - 示例:
     ```javascript
     const users = await User.findAll({
       paranoid: false
     });
     ```
   - SQL 语句: `SELECT * FROM "Users" WHERE "deletedAt" IS NULL`

7.  `nest`
    - 功能: 设置为 true 时,将使用嵌套查询来执行查询,设置为 false 时,将使用连接查询来执行查询
    - 示例:
      ```javascript
      const users = await User.findAll({
        nest: true
      });
      ```
    - SQL 语句: 
      - 嵌套查询: `SELECT * FROM "Users"` 
      - 连接查询: `SELECT "Users".* FROM "Users"`

8.  `distinct`
    - 功能: 设置为 true 时,将使用 DISTINCT 查询来执行查询；使用 DISTINCT 可以从查询结果中去重,只返回唯一的记录
    - 示例:
      ```javascript
      const users = await User.findAll({
        distinct: true
      });
      ```
    - SQL 语句: `SELECT DISTINCT * FROM "Users"`

9.  `required`
    - 功能:
      - 设置为 true 时,它会生成一个 INNER JOIN 语句,只返回那些有关联数据的记录
      - 设置为 false,它会生成一个 LEFT OUTER JOIN 语句,返回所有记录,即使没有关联数据
    - 示例:
      ```javascript
      const users = await User.findAll({
        required: true
      });
      ```
    - SQL 语句: 
      - `required: true`: `SELECT * FROM "Users" INNER JOIN "Skus" ON "Users"."id" = "Skus"."userId"`
      - `required: false`: `SELECT * FROM "Users" LEFT OUTER JOIN "Skus" ON "Users"."id" = "Skus"."userId"`

