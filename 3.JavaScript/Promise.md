

```javascript
const fetchPosts = () => fetch('https://api.example.com/posts').then(response => response.json());
const fetchUsers = () => fetch('https://api.example.com/users').then(response => response.json());

Promise.all([fetchPosts(), fetchUsers()])
  .then(([dataPosts, dataUsers]) => {
    console.log(dataPosts); // 处理获取的帖子数据
    console.log(dataUsers); // 处理获取的用户数据
  })
  .catch(error => {
    console.error('Failed to fetch data:', error);
  });
--------------------------------------------------------
function updateUI(posts, comments) {
  // 假设有用于显示帖子和评论的DOM元素
  const postsContainer = document.getElementById('posts');
  const commentsContainer = document.getElementById('comments');

  postsContainer.innerHTML = posts.map(post => `<div>${post.content}</div>`).join('');
  commentsContainer.innerHTML = comments.map(comment => `<div>${comment.text}</div>`).join('');
}
```

### 应用场景

1. **并行请求**：当你需要并行执行多个网络请求，并且需要所有请求的结果来继续执行下一步操作时。
2. **依赖于多个异步操作**：如果某个操作依赖于多个异步操作的结果，你可以使用 `Promise.all()` 来等待所有这些操作完成。
3. **性能优化**：使用 `Promise.all()` 可以减少等待时间，因为异步操作是并行执行的，而不是顺序执行的。

### 注意事项

- `Promise.all()` 会在任何一个 Promise 失败时立即拒绝，这意味着你可能会错过其他 Promise 成功解决的结果。
- 如果你需要即使在某些 Promise 失败的情况下也获取所有 Promise 的结果，你可能需要分别处理每个 Promise，或者使用其他方法如 `Promise.allSettled()`。