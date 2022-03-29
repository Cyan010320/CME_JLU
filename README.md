<h2>----------------欢迎来到贝拉的直播间----------------</h2>
<h4>B站关注贝拉Kira哦～</h4>
<a href="https://live.bilibili.com/22632424?broadcast_type=0&is_room_feed=1&spm_id_from=333.999.0.0">贝拉的直播间</a>
<br>
<a href="AnotherMarkdown.md">Portal</a>
<br>
<a href="https://i2.hdslb.com/bfs/face/668af440f8a8065743d3fa79cfa8f017905d0065.jpg@240w_240h_1c_1s.webp">头图</a>
```cpp
#include<iostream>

class BinaryTree {

public:

	BinaryTree* LeftLeaf;
	BinaryTree* RightLeaf;
	int data;
	BinaryTree() {
		LeftLeaf = nullptr;
		RightLeaf = nullptr;
		data = 0;
	}
};

BinaryTree* CreateLeaf(BinaryTree* &root) {
	int a;
	std::cin >> a;

	if (a) {
	
		root = new BinaryTree;
		root->data = a;
		root->LeftLeaf = nullptr;
		root->RightLeaf = nullptr;
		CreateLeaf(root->LeftLeaf);
		CreateLeaf(root->RightLeaf);
	}
	else {
		root = nullptr;
	}

	return root;
}

BinaryTree* PreTraverse(BinaryTree* root) {
	if (root) {
		std::cout << root->data << ' ';
		PreTraverse(root->LeftLeaf);
		PreTraverse(root->RightLeaf);
	}
	else return root;


}

BinaryTree* InTraverse(BinaryTree* root) {
	if (root) {
		InTraverse(root->LeftLeaf);
		std::cout << root->data << ' ';
		InTraverse(root->RightLeaf);
	}
	else return root;

}

BinaryTree* PostTraverse(BinaryTree* root) {
	if (root) {
		PostTraverse(root->LeftLeaf);
		PostTraverse(root->RightLeaf);
		std::cout << root->data << ' ';

	}
	else return root;
}


int main() {
	BinaryTree* root = nullptr;
	CreateLeaf(root);
	PreTraverse(root);
	std::cout << std::endl;
	InTraverse(root);
	std::cout << std::endl;
	PostTraverse(root);
	return 0;
}
```
