# Programming problems for Frontend engineers 
- Create and array of 1000 promises and execute them in batches of 10
- ```js
  class LRUCache {
  constructor(size) {
    this.size = size;
    this.cache = new Map();
  }

  get(key) {
    if (!this.cache.has(key)) {
      return -1;
    }
    const value = this.cache.get(key);
    this.cache.delete(key);
    this.cache.set(key, value);
    return value;
  }

  put(key, value) {
    if (this.cache.has(key)) {
      this.cache.delete(key);
    }
    this.cache.set(key, value);
    if (this.cache.size > this.size) {
      console.log(this.cache.keys());
      console.log(this.cache.keys().next());
      const leastUsedKey = this.cache.keys().next();
      this.cache.delete(leastUsedKey.value);
    }
  }
}

const lruCache = new LRUCache(3);

lruCache.put(1, 1); // Cache is {1=1}
lruCache.put(2, 2); // Cache is {1=1, 2=2}
console.log(lruCache.get(1)); // returns 1, Cache is {2=2, 1=1} // 1
lruCache.put(3, 3); // Cache capacity is 2, evicts key 2, Cache is {1=1, 3=3}
console.log(lruCache.get(2)); // returns -1 (not found) // 2
console.log(lruCache.get(1));
lruCache.put(4, 4); // Cache capacity is 2, evicts key 1, Cache is {3=3, 4=4}
console.log(lruCache.get(1)); // returns -1 (not found) // -1
console.log(lruCache.get(3)); // returns 3, Cache is {4=4, 3=3} // 3
console.log(lruCache.get(4)); // returns 4, Cache is {3=3, 4=4} // 4

  ```
- Write a program to implement the LRUCache
