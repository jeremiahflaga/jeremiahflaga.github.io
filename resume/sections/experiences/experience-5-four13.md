<div class="">
    <div class="float-right">
        <span class="text-primary experience-date">June 2018 - June 2019</span>
    </div>
    <div class="">
        <h3 class="mb-0">Software Developer (.NET)</h3>
        <div class="subheading mb-3">
            <a href="https://four13group.com/">Four13 Group</a>
        </div>
        <div class="col-md-10">
            <p>
                Worked on an application used for points-based rewards system for agents in a company.
            </p>
            <p>
                Also involved in a team working on a Customer Relationship Management app for an online store. The CRM generates reports, allows searching for nearby clients, viewing quotes of clients, viewing products and number of stocks available, etc.
            </p>
        </div>
        <p class="col-md-10 small">
            <strong>Technologies used:</strong> ASP.NET MVC, ASP.NET Web API, AngularJS, Entity Framework, Dapper, SQL Server
        </p>
    </div>
</div>


<div class="col-md-10 accordion mt-2 d-print-none d-none" id="experience-5-four13-accordion">
    <div class="card">
        <div class="card-header p-0" id="experience-5-four13-heading-contributions">
            <p class="mb-0">
                <button class="btn btn-link btn-block text-left collapsed subheading-small" type="button" data-toggle="collapse" data-target="#experience-5-four13-collapse-contributions" aria-expanded="true" aria-controls="experience-5-four13-collapse-contributions">
                Contributions:
                </button>
            </p>
        </div>
        <div id="experience-5-four13-collapse-contributions" class="collapse" aria-labelledby="experience-5-four13-heading-contributions" data-parent="#experience-5-four13-accordion">
	        <div class="card-body">
                <div class="pr-3">
                    <p>
                        The first app I worked on has two ways for data access: one uses a database-first model of Entity Framework and the other one uses a code-first model of Entity Framework. This sometimes gets in the way when I'm searching for the model to use when adding features in the app. So I refactored the app so that it will only use the code-first model. Then, when the refactorings was finished, I was able to delete all of the database-first models.
                    </p>
                    <p>
                        It was just a small app and not very complex, so it was doable within a short period of time. I do not advise doing that in medium sized or big apps.
                    </p>
                </div>
            </div>
        </div>
    </div>
    <div class="card">
        <div class="card-header p-0" id="experience-5-four13-heading-lessons-learned">
	        <p class="mb-0">
	            <button class="btn btn-link btn-block text-left collapsed subheading-small" type="button" data-toggle="collapse" data-target="#experience-5-four13-collapse-lessons-learned" aria-expanded="false" aria-controls="experience-5-four13-collapse-lessons-learned">
	            Dis-contributions:
	            </button>
	        </p>
        </div>
        <div id="experience-5-four13-collapse-lessons-learned" class="collapse" aria-labelledby="experience-5-four13-heading-lessons-learned" data-parent="#experience-5-four13-accordion">
	        <div class="card-body">
                <div class="pr-3">
                    <p>
                        I was the only one working on my first project in the company so it seemed to me that I was free to do whatever I wanted with the codebase.
                    </p>
                    <p>
                        There was a test module in the project, but it was empty. I thought to myself, "Maybe the original developer wanted to create tests but did not have time to create it; let me try". The codebase was not structured to be testable, so I decided to re-structure things...
                    </p>
                    <div class="mb-3">
                        <table>
                            <tbody>
                                <tr>
                                    <td>... from this: &nbsp;&nbsp;&nbsp;</td>
                                    <td>
                                        <a href="https://blog.ploeh.dk/2013/12/03/layers-onions-ports-adapters-its-all-the-same/">
                                            <img src="/images/2021/2021-05-22-simple-diagram-layered-architecture.png" height="250">
                                        </a>
                                    </td>
                                    <td>&nbsp;&nbsp;&nbsp; ... to this: &nbsp;&nbsp;&nbsp;</td>
                                    <td>
                                        <a href="https://blog.ploeh.dk/2013/12/03/layers-onions-ports-adapters-its-all-the-same/">
                                            <img src="/images/2021/2021-05-22-simple-diagram-clean-architecture.png" height="250">
                                        </a>
                                    </td>
                                </tr>
                                <!-- <tr>
                                    <td colspan="4">
                                        <small>(images are from Mark Seeman's post, <a href="https://blog.ploeh.dk/2013/12/03/layers-onions-ports-adapters-its-all-the-same/">"Layers, Onions, Ports, Adapters: it's all the same"</a>)</small>
                                    </td>
                                </tr> -->
                            </tbody>
                        </table>
                    </div>
                    <p>
                        ... to make the code testable.
                    </p>
                    <p>
                        I was able to setup the tests, and then managed to create some unit tests and some acceptance tests, but I later abandoned them for some reasons... 
                    </p>
                    <p>
                        The major reason why the tests were abandoned was this: When I started working on the project, I have this kind of mindset which says something like <em>"I have all the time in the world to work for this project, and so I will be able to write all the tests needed".</em> Well, I later learned that the client does not have all the time in the world to give to me. Worse, I needed to work somewhere else so I have to resign from the job.
                    </p>                    
                    <p>
                        Because of the restructuring that I did, the project now has two different structures: the original one, and the other one which makes the code easier to test. Poor guy who inherited the codebase. I hope he can be able to find which code uses which structure.
                    </p>                
                    <p>
                        ... More than a year later, when I am already working in another company, I came across these words from the book <a href="https://www.bookdepository.com/Mythical-Man-Month-Frederick-P-Brooks-Jr/9780201835953?a_aid=jflaga">"The Mythical Man-Month"</a> by Frederick P. Brooks:
                    </p>
                    <blockquote>                  
                        <p>
                            I will contend that conceptual integrity is the most important consideration in system design. It is better to have a system omit certain anomalous features and improvements, but to reflect one set of design ideas, than to have one that contains many good but independent and uncoordinated ideas.
                        </p>
                        <p>
                            ... I will certainly not contend that only the architects will have good architectural ideas. Often the fresh concept does come from an implementer or from a user. However, all my own experience convinces me, and I have tried to show, that <strong>the conceptual integrity of a system determines its ease of use</strong>. Good features and ideas that do not integrate with a system's basic concepts are best left out. If there appear many such important but incompatible ideas, one scraps the whole system and starts again on an integrated system with different basic concepts.
                        </p>
                    </blockquote>
                    <p>
                        I think the lesson to be learned in that is that if one decides to restructure a codebase, because he finds it hard to work with that codebase if he will not do so, he must choose a structure that is not too different from the existing one, but still makes the codebase easier to work with.
                    </p>
                    <p>
                        I think that changing it to a completely different structure is acceptable only if the original restructur-er will be involved in the project for a long time or until the restructuring is completed.
                    </p>
                    <!-- <p>
                        <small>(* the images in this section are from Mark Seeman's post, <a href="https://blog.ploeh.dk/2013/12/03/layers-onions-ports-adapters-its-all-the-same/">"Layers, Onions, Ports, Adapters: it's all the same"</a>)</small>
                    </p>                     -->
	            </div>
	        </div>
        </div>
    </div>
</div>

<div class="mb-5">

</div>
