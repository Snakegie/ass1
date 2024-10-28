# ass1
#include <iostream>
#include <vector>
#include <string>

using namespace std;

// 定义联系人类
class Contact {
public:
	string name;    // 联系人姓名
	string phone;   // 联系人电话
	string email;   // 联系人电子邮件
	
	// 构造函数，初始化联系人信息
	Contact(string n, string p, string e) : name(n), phone(p), email(e) {}
};

// 定义联系人管理类
class ContactManager {
private:
	vector<Contact> contacts;  // 存储联系人的 vector
	
public:
	// 添加联系人函数
	void add_contact(const string& name, const string& phone, const string& email) {
		Contact new_contact(name, phone, email);
		contacts.push_back(new_contact);
		cout << "联系人已成功添加！" << endl;
	}
	
	// 显示所有联系人
	void display_contacts() const {
		for (const auto& contact : contacts) {
			cout << "姓名: " << contact.name << ", 电话: " << contact.phone << ", 邮件: " << contact.email << endl;
		}
	}
};

// 主函数
int main() {
	ContactManager manager;
	
	// 添加联系人示例
	manager.add_contact("张三", "123-456-7890", "zhangsan@example.com");
	manager.add_contact("李四", "987-654-3210", "lisi@example.com");
	
	// 显示所有联系人
	manager.display_contacts();
	
	return 0;
}
