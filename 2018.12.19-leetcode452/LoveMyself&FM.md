class Solution {
public:
    int findMinArrowShots(vector<pair<int, int>>& points) {
    	
    	
    	int n=points.size();
    	if(n==0) return 0;
		sort(points.begin(),points.end(),mycmp);
		int icount=1;
		int tp=points[0].second;
		for(int i=1;i<n;i++)
		{
			if(tp>=points[i].first)
			{
				continue;
			}
			else
			{
				tp=points[i].second;
				icount++;
			}
		} 
		return icount;
        
    }
    
    static bool mycmp(pair<int, int> a,pair<int, int> b)
    {
    	if(a.second!=b.second)
    	return a.second<b.second;
    	else
    	return a.first<b.first;
    }
};
