<div class="">
    <div class="float-right">
        <span class="text-primary experience-date">October 2016 - May 2018</span>
    </div>
    <div class="">
        <h3 class="mb-0">Software Developer (Android)</h3>
        <div class="subheading mb-3">
            <a href="http://www.myndconsulting.com/">Mynd Consulting</a>
        </div>
        <p class="col-md-10">Involved in the maintenance of an Android app for a TV show.</p>
        <p class="col-md-10 small">
            <strong>Technologies used:</strong> Java, Android Framework, RxJava, SugarORM, etc.
        </p>
    </div>
</div>


<div class="col-md-10 accordion mt-2 d-print-none d-none" id="experience-4-mynd-accordion">
    <div class="card">
        <div class="card-header p-0" id="experience-4-mynd-heading-contributions">
            <p class="mb-0">
                <button class="btn btn-link btn-block text-left collapsed subheading-small" type="button" data-toggle="collapse" data-target="#experience-4-mynd-collapse-contributions" aria-expanded="true" aria-controls="experience-4-mynd-collapse-contributions">
                Contributions:
                </button>
            </p>
        </div>
        <div id="experience-4-mynd-collapse-contributions" class="collapse" aria-labelledby="experience-4-mynd-heading-contributions" data-parent="#experience-4-mynd-accordion">
	        <div class="card-body">
                <div class="pr-3">
                    <p>
                        Nothing extraordinary. Just finished the tasks assigned to me.
                    </p>
                    <p>
                        But this time, because I already have a better understanding of polymorphism (and its use), and the SOLID principles, and other things related to software design, I tried to use these knowledge in my coding.
                    </p>
                </div>
            </div>
        </div>
    </div>
    <div class="card">
        <div class="card-header p-0" id="experience-4-mynd-heading-lessons-learned">
	        <p class="mb-0">
	            <button class="btn btn-link btn-block text-left collapsed subheading-small" type="button" data-toggle="collapse" data-target="#experience-4-mynd-collapse-lessons-learned" aria-expanded="false" aria-controls="experience-4-mynd-collapse-lessons-learned">
	            Lessons Learned:
	            </button>
	        </p>
        </div>
        <div id="experience-4-mynd-collapse-lessons-learned" class="collapse" aria-labelledby="experience-4-mynd-heading-lessons-learned" data-parent="#experience-4-mynd-accordion">
	        <div class="card-body">
                <div class="pr-3">
                    <ol>
                        <li>
                            <p>
                                I learned how to work on a Java platform.
                            </p>
                            <p>
                                Before this job, I only knew how to do real world apps using .NET.
                            </p>
                            <p>
                                Doing Android made me more confident that I can also do work on other platforms. (Big thanks to my employer for giving me this job even though I had almost no experience with Android development.)
                            </p>
                        </li>
                        <li>
                            <p>
                                Even though we were using <a href="/2018/05/23/rxjava-is-not-intuitive/">RxJava</a> in our project, which others say makes dealing with threading much easier, there was a time where I had to deal with what they call a <em>race condition</em> with this <em>threads</em> thing while working on version 2 of the app. 
                            </p>
                            <p>
                                It was hard. The bug was intermittent. It was hard to find, [partly because <a href="/2018/05/23/rxjava-is-not-intuitive/">that part of the project uses RxJava in a wrong way(?)</a>
                                After I few weeks/months working on the project I discovered that when using RxJava, methods must return <code>Observables</code> all the way up from the data source to the presentation layer, to avoid memory leaks and so that they can be easily composed.
                            </p>
                            <p>
                                But I'm not 100% sure if the wrong way of using RxJava is truly the reason for that bug. Perhaps it was just my ignorance on how to deal with threads.
                                Luckily, that feature was removed during the development of version 3 of the app. <em>Yehey!</em>
                            </p>
                            <p>
                                I still have to learn more about this <em>threads</em> thing.
                            </p>
                        </li>
                    </ol>
	            </div>
	        </div>
        </div>
    </div>
</div>

<div class="mb-5">

</div>
