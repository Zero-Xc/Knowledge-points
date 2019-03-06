### 新建一个泛型实体类
```
  public class UserPojo<T> {
	
    private int total;
    /** 具体的内容. */
    private T data;
	public int getTotal() {
		return total;
	}
	public void setTotal(int total) {
		this.total = total;
	}
	public T getData() {
		return data;
	}
	public void setData(T data) {
		this.data = data;
	}

    
}
```

### 新建一个工具类
```
  import com.util.UserPojo;

public class UserUtil {
	public static UserPojo<Object> success(Object object,int total) {
		UserPojo<Object> result = new UserPojo<Object>();
        result.setData(object);
        result.setTotal(total);
        return result;
    }
}
```

### 在controller中使用即可
```
@RequestMapping(value="admin/getUserListPage",method=RequestMethod.GET)
	public UserPojo<Object> getUserList(@RequestParam int page)  {
		return UserUtil.success(usermapper.getUserList(page), usermapper.getSum());
	}
```
