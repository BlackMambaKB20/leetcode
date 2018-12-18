class Solution {
    public int eraseOverlapIntervals(Interval[] intervals) {

        if(intervals.length == 0)
            return 0;

        Arrays.sort(intervals, new Comparator<Interval>(){
            public int compare(Interval o1, Interval o2){
                if(o1.end != o2.end)
                    return o1.end - o2.end;
                return o1.start - o2.start;       
            }
        });

        int res = 1;
        int pre = 0;
        for(int i=1; i<intervals.length; i++)
            if(intervals[i].start >= intervals[pre].end){
                res++;
                pre = i;
            }
        return intervals.length - res;
    }
}
