#include <reg51.h>

unsigned char calculate_checksum(unsigned char arr[], unsigned char n) {
	unsigned char checksum = 0;
	unsigned char sum = 0;
	 unsigned char i;
	for (i = 0; i < n; i++) {
		sum += arr[i];
	}
	checksum = ~sum; 
	return checksum;
}
bit checksumvalid(unsigned char arr[], unsigned char n, unsigned char received_checksum) {
	unsigned char sum = 0;
	unsigned char i;
	for (i = 0; i < n; i++) {
		sum += arr[i];
	}
	sum += received_checksum; 
	return (sum == 0xFF); 
}
void main(void) {
	unsigned char mydata[] = {0x25, 0x62, 0x3F, 0x52, 0xE8};
	unsigned char mydata1[] = {0x24, 0x62, 0x3F, 0x52, 0xE8};
	unsigned char checksum;
	bit isvalid;
	checksum = calculate_checksum(mydata, sizeof(mydata));
	isvalid = checksumvalid(mydata1, sizeof(mydata1), checksum);
	if (isvalid) {
		P0 = 0x47;  
	} 
	else 
		{
			P0 = 0x42;  
		}
}
