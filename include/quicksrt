template<class It>
void quick_sort1(It first, It last) {

	if (first < last - 1) {
		It pivot = partition(first, last);
		quick_sort(first, pivot);
		quick_sort(pivot, last);
	}
}
template<class It>
void quick_sort2(It first , It last) {

	It right = last - 1;
	It left = first;
	It middle = right;

	for(It i = left; middle > i; ++i, --middle);

	do {
		while ( *left < *middle ){
			++left;
		}
		while ( *right > *middle ){
			--right;
		}

		if (left <= right) {
			std::iter_swap(left, right);
			if(middle == right){
				middle = left;
			} else {
				if(middle == left){
					middle = right;
				}
			}
			++left;
			--right;
		}
	} while ( left <= right );

	if ( right > first ){
		quick_sort2(first, right + 1);
	}
	if ( last > left + 1){
		quick_sort2(left, last);
	}
}
template<class It>
It partition(It first, It last) {

	auto pivot = *(last - 1);
	It i = first - 1;
	for (It j = first; j < last - 1; ++j) {
		if (*j <= pivot) {
			++i;
			std::iter_swap(i, j);
		}
	}
	std::iter_swap(i + 1, last - 1);

	return i + 1;
}
