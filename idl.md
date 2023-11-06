```
partial interface Document {
  Promise<StorageAccessHandle> requestStorageAccess(StorageAccessTypes types);
};

dictionary StorageAccessTypes {
  boolean all = false;
  boolean estimate = false;
  boolean persisted = false;
  boolean persist = false;
  boolean sessionStorage = false;
  boolean localStorage = false;
  boolean indexedDB = false;
  boolean locks = false;
  boolean caches = false;
  boolean getDirectory = false;
  boolean createObjectURL = false;
  boolean revokeObjectURL = false;
  boolean BroadcastChannel = false;
  boolean SharedWorker = false;
};

interface StorageAccessHandle {
  Promise<StorageEstimate> estimate();
  Promise<boolean> persisted();
  Promise<boolean> persist();
  readonly attribute Storage sessionStorage;
  readonly attribute Storage localStorage;
  readonly attribute IDBFactory indexedDB;
  readonly attribute LockManager locks;
  readonly attribute CacheStorage caches;
  Promise<FileSystemDirectoryHandle> getDirectory();
  DOMString createObjectURL((Blob or MediaSource) obj);
  undefined revokeObjectURL(DOMString url);
};

[Exposed=StorageAccessHandle]
partial interface BroadcastChannel {};

[Exposed=StorageAccessHandle]
partial interface SharedWorker {};
```