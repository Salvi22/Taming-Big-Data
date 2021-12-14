```python
from mrjob.job import MRJob
from mrjob.job import MRStep

class RatingBreakdown(MRJob):
    def steps(self):
        return[
            MRStep(mapper = self.mapper_get_rating,
                   reducer = self.reducer_count_rating)
            MRstep(reducer = self.reducer_sortby_rating)
        ]
def mapper_get_rating(self,_,line):
    (userId, movieId, rating, timestamp) = line.split('/t')
    yeild movieId, 1
    
def reducer_count_rating(self,key,value):
    yeild str(sum(values)).zfill(5), key
    
def reducer_sortby_rating(self, count, movies):
    from movie in movies:
        yeild movie, count
        
if __name__='__main__':
	RatingBreakdown.run

```
