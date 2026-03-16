---
title: "Resume"
date: 2022-06-13T21:28:51+01:00
draft: false

showDate : false
showDateOnlyInArticle : false
showDateUpdated : false
showHeadingAnchors : false
showPagination : false
showReadingTime : false
showTableOfContents : true
showTaxonomies : false 
showWordCount : false
showSummary : false
sharingLinks : false
showEdit: false
showViews: false
showLikes: false
layoutBackgroundHeaderSpace: false

---

<style>
.timeline-container {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
}
.timeline-section {
  margin-bottom: 40px;
}
.timeline-title {
  font-size: 20px;
  font-weight: bold;
  color: #333;
  margin-bottom: 20px;
  padding-bottom: 10px;
  border-bottom: 2px solid #e0e0e0;
}
.timeline-item {
  display: flex;
  margin-bottom: 25px;
  position: relative;
}
.timeline-item:last-child {
  margin-bottom: 0;
}
.timeline-dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: #546e7a;
  margin-right: 20px;
  margin-top: 6px;
  flex-shrink: 0;
  position: relative;
}
.timeline-dot::before {
  content: '';
  position: absolute;
  top: 12px;
  left: 5px;
  width: 2px;
  height: calc(100% + 25px);
  background: #e0e0e0;
  z-index: -1;
}
.timeline-item:last-child .timeline-dot::before {
  display: none;
}
.timeline-content {
  flex: 1;
}
.timeline-header {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  margin-bottom: 8px;
  flex-wrap: wrap;
  gap: 10px;
}
.timeline-company {
  font-size: 16px;
  font-weight: bold;
  color: #333;
}
.timeline-period {
  font-size: 14px;
  color: #666;
}
.timeline-position {
  font-size: 15px;
  color: #546e7a;
  margin-bottom: 8px;
}
.timeline-description {
  font-size: 14px;
  color: #666;
  line-height: 1.6;
}
.timeline-description ul {
  margin: 8px 0;
  padding-left: 20px;
}
.timeline-description li {
  margin: 4px 0;
}
/* 教育部分特殊样式 */
.education .timeline-dot {
  background: #4caf50;
}
.education .timeline-company {
  color: #2e7d32;
}
/* 工作部分特殊样式 */
.work .timeline-dot {
  background: #2196f3;
}
.work .timeline-company {
  color: #1565c0;
}
/* 响应式 */
@media (max-width: 600px) {
  .timeline-header {
    flex-direction: column;
  }
  .timeline-period {
    order: -1;
  }
}
</style>

## Education
<div class="timeline-container">
  <div class="timeline-section education">
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="timeline-content">
        <div class="timeline-header">
          <span class="timeline-company">University of Toronto</span>
          <span class="timeline-period">Sep 2021 - Aug 2022</span>
        </div>
        <div class="timeline-position">Master of Engineering</div>
        <div class="timeline-description">
            Electrical & Computer Engineering
        </div>
      </div>
    </div>
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="timeline-content">
        <div class="timeline-header">
          <span class="timeline-company">University of Waterloo</span>
          <span class="timeline-period">Jan 2017 - Apr 2021</span>
        </div>
        <div class="timeline-position">Bachelor of Mathematics</div>
        <div class="timeline-description">
            Triple Majored in:
            <ul>
                <li>Computer Science</li>
                <li>Statistics</li>
                <li>Combinatorics & Optimization</li>
            </ul>
        </div>
      </div>
    </div>
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="timeline-content">
        <div class="timeline-header">
          <span class="timeline-company">High School Affiliated to Nanjing Normal University</span>
          <span class="timeline-period">Sep 2013 - Aug 2016</span>
        </div>
        <div class="timeline-position">High School Diploma</div>
      </div>
    </div>
  </div>
</div>

## Work Experience
<div class="timeline-container">
  <div class="timeline-section work">
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="timeline-content">
        <div class="timeline-header">
          <span class="timeline-company">StackAdapt</span>
          <span class="timeline-period">Nov 2022 - Present</span>
        </div>
        <div class="timeline-position">Machine Learning Engineer</div>
      </div>
    </div>
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="timeline-content">
        <div class="timeline-header">
          <span class="timeline-company">Autonomic</span>
          <span class="timeline-period">Sep 2019 - Dec 2019</span>
        </div>
        <div class="timeline-position">Software Engineer Co-op</div>
      </div>
    </div>
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="timeline-content">
        <div class="timeline-header">
          <span class="timeline-company">RSVP.ai</span>
          <span class="timeline-period">Sep 2018 - Dec 2018</span>
        </div>
        <div class="timeline-position">Associate Software Engineer</div>
      </div>
    </div>
    <div class="timeline-item">
      <div class="timeline-dot"></div>
      <div class="timeline-content">
        <div class="timeline-header">
          <span class="timeline-company">Integrated Device Technology</span>
          <span class="timeline-period">Jan 2018 - Dec 2018</span>
        </div>
        <div class="timeline-position">Algorithm Engineer Co-op</div>
      </div>
    </div>
  </div>
</div>

