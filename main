data segment
	cn	dw	4
	res	dw	?
	divisor	db	?
data ends

code segment
	assume cs:code,ds:data
start:	mov ax,data
	mov ds,ax
	mov bx,cn
	call factor
	mov res,ax
	mov divisor,0ah
	div divisor
	
	mov dl,al
	add dl,30h
	mov ah,02h
	int 21h
	
	mov ax,res
	div divisor
	mov dl,ah
	add dl,30h
	mov ah,02h
	int 21h
	
	mov ah,4ch
	int 21h

factor proc near
	
	push ax
	mov ax,bx
	cmp bx,0
	je m0
	cmp bx,1
	je m0
	dec bx
	call factor
	mul bx
	pop bx
	ret
m0:	mov ax,1
	pop bx
	ret

factor endp

code ends

end start
