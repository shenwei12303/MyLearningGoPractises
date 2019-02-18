//学习循环队列（会浪费一个数组空间）
package main

import "fmt"

type Cri struct {
	items []string
	n int
	head int
	tail int
}

func NewCri(cap int) *Cri {
	return &Cri{
		items : make([]string, cap),
		n : cap,
		head : 0,
		tail : 0,
	}
}

//入队
func (this *Cri) Enqueue(item string) bool {
  //检查队列是否已满
	if (this.tail + 1) % this.n == this.head {return false}
	this.items[this.tail] = item
	this.tail = (this.tail + 1) % this.n
	return true
}

//出队
func (this *Cri) Dequeue() string {
  //检查队列是否为空
	if this.head == this.tail {return ""}
	res := this.items[this.head]
	this.head = (this.head + 1) % this.n
	return res
}
