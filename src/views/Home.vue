<template>
    <div class="page new-skin">
		
		<!-- preloader -->
		<div class="preloader">
			<div class="centrize full-width">
				<div class="vertical-center">
					<div class="spinner">
						<div class="double-bounce1"></div>
						<div class="double-bounce2"></div>
					</div>
				</div>
			</div>
		</div>

		<!-- background -->
		<div class="background"></div>

		<!--
			Container
		-->
		<div class="container opened" data-animation-in="fadeInLeft" data-animation-out="fadeOutLeft">

			<!--
				Header
			-->
			<header class="header">
                    
				<!-- header profile -->
				<div class="profile">
                    <div class="title">{{profile.fullname}}</div>
					<div class="subtitle subtitle-typed">
						<div class="typing-title">
                            <p v-for="(work, index) in profile.work" :key="index">{{work}}</p>
						</div>
					</div>
				</div>

				<!-- menu btn -->
				<!--<a href="#" class="menu-btn"><span></span></a>-->

				<!-- menu -->
				<div class="top-menu">
					<ul>
						<li class="active">
							<a href="#about-card">
								<span class="icon ion-person"></span>
								<span class="link">Bio</span>
							</a>
						</li>
						<li>
							<a href="#resume-card">
								<span class="icon ion-android-list"></span>
								<span class="link">Resume</span>
							</a>
						</li>
						<li v-if="false">
							<a href="#works-card">
								<span class="icon ion-android-create"></span>
								<span class="link">Works</span>
							</a>
						</li>
						<li v-if="false">
							<a href="#blog-card">
								<span class="icon ion-chatbox-working"></span>
								<span class="link">Blog</span>
							</a>
						</li>
						<li>
							<a href="#contacts-card">
								<span class="icon ion-at"></span>
								<span class="link">Contact</span>
							</a>
						</li>
					</ul>
				</div>

			</header>

			<!--
				Card - Started
			-->
			<div class="card-started" id="home-card">

				<!--
					Profile
				-->
				<div class="profile no-photo">

					<!-- profile image -->
					<div class="slide" :style="'background-image: url('+profile.images+');'"></div>

					<!-- profile titles -->
					<div class="title" style="font-size: 24px;">{{profile.fullname}}</div>
					<div class="category">{{profile.nickname}}</div>
					<div class="subtitle subtitle-typed">
						<div class="typing-title">
							<p v-for="(work, index) in profile.work" :key="index">{{work}}</p>
						</div>
					</div>

					<!-- profile socials -->
					<div class="social">
						<a target="_blank" :href="profile.social.facebook">
							<span class="fa fa-facebook-f"></span>
						</a>
						<a target="_blank" :href="profile.social.linkedin">
							<span class="fa fa-linkedin"></span>
						</a>
						<a target="_blank" :href="profile.social.github">
							<span class="fa fa-github"></span>
						</a>
					</div>
					
					<!-- profile buttons -->
					<div class="lnks">
						<a href="#" class="lnk">
							<span class="text">Download CV</span>
							<span class="ion ion-android-attach"></span>
						</a>
						<a href="#" class="lnk discover">
							<span class="text">Contact Me</span>
							<span class="ion ion-android-mail"></span>
						</a>
					</div>

				</div>

			</div>

			<!-- 
				Card - About
			-->
			<div class="card-inner animated active" id="about-card">
				<div class="card-wrap">

					<!-- 
						About 
					-->
					<div class="content about">

						<!-- title -->
						<div class="title">About Me</div>

						<!-- content -->
						<div class="row">
							<div class="col col-d-6 col-t-6 col-m-12 border-line-v">
								<div class="text-box">
									<p>
                                        <!-- ฉันเป็นนักวางแผนรูปแบบการทำงาน และนักพัฒนาเว็บฉันเรียนจบด้านการพัฒนาซอฟต์แวร์โดยตรงและพัฒนาเว็บไซต์ให้กับหน่วยงานระดับประเทศและหน่วยงานราชการที่มีชื่อเสียงหลายแห่งและในช่วง 10 ปีที่ผ่านมาฉันมีประสบการณ์เกี่ยวกับเว็บไซต์เกือบทุกประเภท -->
                                        {{profile.about}}
									</p>
								</div>
							</div>
							<div class="col col-d-6 col-t-6 col-m-12 border-line-v">
								<div class="info-list">
									<ul>
										<li><strong>Age . . . . .</strong> {{birthYear}}</li>
										<li><strong>Residence . . . . .</strong> {{profile.county}}</li>
										<li><strong>Freelance . . . . .</strong> {{profile.freelance}}</li>
										<li><strong>Address . . . . .</strong> {{profile.address}}, {{profile.county}}</li>
									</ul>
								</div>
							</div>
							<div class="clear"></div>
						</div>

					</div>

					<!--
						Awards
					-->
					<div class="content services">

						<!-- title -->
						<div class="title">Awards</div>

						<!-- content -->
						<div class="row service-items border-line-v">
							<!-- service item -->
							<div class="col col-d-6 col-t-6 col-m-12 border-line-h" v-for="(award, index) in profile.awards.list" :key="index">
								<div class="service-item">
									<div class="icon">
										<span class="fa fa-trophy"></span>
									</div>
									<div class="name">
										<span >{{award.title}}</span>
									</div>
									<div class="desc">
										<div >
											{{award.desc}}
										</div>
									</div>
								</div>
							</div>
						</div>

						<div class="clear"></div>

						<!-- content -->
						<div class="row">
							<div class="col col-d-12 col-t-12 col-m-12 border-line-v">
								<div class="revs-item">
									<div class="text">
										<div >
											{{profile.awards.desc}}
										</div>
									</div>
									<div class="user">
										<div class="img">
											<img :src="profile.awards.images" alt="{{profile.awards.fullname}}" />
										</div>
										<div class="info">
											<div class="name">{{profile.awards.fullname}}</div>
											<div class="company">{{profile.awards.work}}</div>
										</div>
										<div class="clear"></div>
									</div>
								</div>
							</div>
							<div class="clear"></div>
						</div>

					</div>
                    

				</div>
			</div>

			<!--
				Card - Resume
			-->
			<div class="card-inner" id="resume-card">
				<div class="card-wrap">

					<!--
						Resume
					-->
					<div class="content resume">

						<!-- title -->
						<div class="title">Resume</div>

						<!-- content -->
						<div class="row">

							<!-- experience -->
							<div class="col col-d-6 col-t-6 col-m-12 border-line-v">
								<div class="resume-title border-line-h">
									<div class="icon"><i class="fa fa-briefcase"></i></div>
									<div class="name">Experience</div>
								</div>
								<div class="resume-items">
									<div :class="'resume-item border-line-h '+ (item.isActive ? 'active': '')" v-for="(item, index) in profile.resume.experiences" :key="index">
										<div class="date" v-html="item.year"></div>
										<div class="name" v-html="item.subject"></div>
										<div class="company" v-html="item.title"></div>
										<p v-html="item.desc"></p>
									</div>
								</div>
							</div>

							<!-- education -->
							<div class="col col-d-6 col-t-6 col-m-12 border-line-v">
								<div class="resume-title border-line-h">
									<div class="icon"><i class="fa fa-university"></i></div>
									<div class="name">Education</div>
								</div>
								<div class="resume-items">
                                    <div :class="'resume-item border-line-h '+ (item.isActive ? 'active': '')" v-for="(item, index) in profile.resume.educations" :key="index">
										<div class="date" v-html="item.year"></div>
										<div class="name" v-html="item.subject"></div>
										<div class="company" v-html="item.title"></div>
										<p v-html="item.desc"></p>
									</div>
								</div>
							</div>

							<div class="clear"></div>
						</div>

					</div>

					<!--
						Skills
					-->
					<div class="content skills">

						<!-- title -->
						<div class="title">Skills</div>
					
						<!-- content -->
						<div class="row">
						
							<!-- skill item -->
							<div class="col col-d-12 col-t-12 col-m-12 border-line-v">
								<div class="skills-list">
									<ul>
										<li :class="index == profile.skills.length - 1 ? 'border-line-h': ''" v-for="(skill, index) in profile.skills" :key="index"> 
											<div class="name">{{skill.title}}</div>
											<div class="progress">
												<div class="percentage" :style="'width:'+skill.scale+';'"></div>
											</div>
										</li>
									</ul>
								</div>
							</div>

							<!-- skill item -->
							<div class="col col-d-6 col-t-6 col-m-12 border-line-v">
								<div class="skills-list dotted">
									<div class="skill-title border-line-h">
										<div class="icon"><i class="fa fa-flag"></i></div>
										<div class="name">Languages</div>
									</div>
									<ul>
                                        <li :class="index == profile.languages.length - 1 ? 'border-line-h': ''" v-for="(language, index) in profile.languages" :key="index"> 
											<div class="name">{{language.title}}</div>
											<div class="progress">
												<div class="percentage" :style="'width:'+language.scale+';'"></div>
											</div>
										</li>
									</ul>
								</div>
							</div>

							<!-- skill item -->
							<div class="col col-d-6 col-t-6 col-m-12 border-line-v">
								<div class="skills-list list">
									<div class="skill-title border-line-h">
										<div class="icon"><i class="fa fa-list"></i></div>
										<div class="name">Knowledge</div>
									</div>
									<ul>
										<li v-for="(knowledge, index) in profile.knowledges" :key="index"> 
											<div class="name">{{knowledge}}</div>
										</li>
									</ul>
								</div>
							</div>
							
							<div class="clear"></div>
						</div>
						
					</div>


                    <!--
						Certificate
					-->
					<div class="content clients">

						<!-- title -->
						<div class="title">Certificates</div>

						<!-- content -->
						<div class="row client-items">

							<!-- client item -->
							<div class="col col-d-4 col-t-4 col-m-12 photo border-line-v" v-for="(certificate, index) in profile.certificates" :key="index">
								<!-- <div class="client-item">
									<div class="image">
										<a target="_blank" :href="certificate.link">
											<img :src="certificate.image" alt="" />
                                            <small v-html="certificate.title"></small>
										</a>
									</div>
								</div> -->

                                <div class="box-item" v-if="certificate.images.length == 1">
									<div class="image">
										<a :href="certificate.images[0]" class="has-popup-image">
											<img :src="certificate.images[0]" :alt="certificate.category" />
											<span class="info">
												<span class="ion ion-image"></span>
											</span>
										</a>
									</div>
									<div class="desc">
										<a :href="certificate.images[0]" class="name has-popup-image" v-html="certificate.title"></a>
										<div class="category">{{certificate.category}}</div>
									</div>
								</div>

                                <div class="box-item" v-else-if="certificate.images.length > 1">
									<div class="image">
										<a :href="'#gallery-'+index" class="has-popup-gallery">
											<img :src="certificate.images[0]" :alt="certificate.category" />
											<span class="info">
												<span class="ion ion-images"></span>
											</span>
										</a>
										<div :id="'gallery-'+index" class="mfp-hide">
											<a :href="image" v-for="(image, imageIndex) in certificate.images" :key="imageIndex"></a>
										</div>
									</div>
									<div class="desc">
										<a :href="'#gallery-'+index" class="name has-popup-gallery" v-html="certificate.title"></a>
										<div class="category">{{certificate.category}}</div>
									</div>
								</div>

                                <div class="box-item" v-else>
									<div class="image">
										<a :href="profile.no_images" class="has-popup-image">
											<img :src="profile.no_images" :alt="certificate.category" />
											<span class="info">
												<span class="ion ion-image"></span>
											</span>
										</a>
									</div>
									<div class="desc">
										<a :href="profile.no_images" class="name has-popup-image" v-html="certificate.title"></a>
										<div class="category">{{certificate.category}}</div>
									</div>
								</div>

							</div>

							<div class="clear"></div>
						</div>

					</div>

				</div>
			</div>

			<!--
				Card - Works
			-->
			<div class="card-inner" id="works-card" v-if="false">
				<div class="card-wrap">

					<!--
						Works
					-->
					<div class="content works">

						<!-- title -->
						<div class="title">Recent Works</div>

						<!-- filters -->
						<div class="filter-menu filter-button-group">
							<div class="f_btn active">
								<label><input type="radio" name="fl_radio" value="grid-item" />All</label>
							</div>
							<div class="f_btn">
								<label><input type="radio" name="fl_radio" value="photo" />Image</label>
							</div>
							<div class="f_btn">
								<label><input type="radio" name="fl_radio" value="gallery" />Gallery</label>
							</div>
							<div class="f_btn">
								<label><input type="radio" name="fl_radio" value="video" />Video</label>
							</div>
							<div class="f_btn">
								<label><input type="radio" name="fl_radio" value="music" />Music</label>
							</div>
							<div class="f_btn">
								<label><input type="radio" name="fl_radio" value="design" />Content</label>
							</div>
						</div>

						<!-- content -->
						<div class="row grid-items border-line-v">

							<!-- work item photo -->
							<div class="col col-d-6 col-t-6 col-m-12 grid-item photo border-line-h">
								<div class="box-item">
									<div class="image">
										<a href="images/wwork1.jpg" class="has-popup-image">
											<img src="images/wwork1.jpg" alt="" />
											<span class="info">
												<span class="ion ion-image"></span>
											</span>
										</a>
									</div>
									<div class="desc">
										<a href="images/wwork1.jpg" class="name has-popup-image">Best Resumes Writing</a>
										<div class="category">Image</div>
									</div>
								</div>
							</div>

							<!-- work item video -->
							<div class="col col-d-6 col-t-6 col-m-12 grid-item video border-line-h">
								<div class="box-item">
									<div class="image">
										<a href="https://vimeo.com/97102654" class="has-popup-video">
											<img src="images/wwork2.jpg" alt="" />
											<span class="info">
												<span class="ion ion-videocamera"></span>
											</span>
										</a>
									</div>
									<div class="desc">
										<a href="https://vimeo.com/97102654" class="name has-popup-video">Vintage Design Book</a>
										<div class="category">Video</div>
									</div>
								</div>
							</div>

							<!-- work item music -->
							<div class="col col-d-6 col-t-6 col-m-12 grid-item music border-line-h">
								<div class="box-item">
									<div class="image">
										<a href="https://w.soundcloud.com/player/?visual=true&url=http%3A%2F%2Fapi.soundcloud.com%2Ftracks%2F221650664&show_artwork=true" class="has-popup-music">
											<img src="images/wwork3.jpg" alt="" />
											<span class="info">
												<span class="ion ion-music-note"></span>
											</span>
										</a>
									</div>
									<div class="desc">
										<a href="#" class="name has-popup">Vintage Black Book</a>
										<div class="category">Music</div>
									</div>
								</div>
							</div>

							<!-- work item design -->
							<div class="col col-d-6 col-t-6 col-m-12 grid-item design border-line-h">
								<div class="box-item">
									<div class="image">
										<a href="#popup-1" class="has-popup-media">
											<img src="images/wwork4.jpg" alt="" />
											<span class="info">
												<span class="ion ion-images"></span>
											</span>
										</a>
									</div>
									<div class="desc">
										<a href="#popup-1" class="name has-popup-media">Blue Book of Recipes</a>
										<div class="category">Content</div>
									</div>
									<div id="popup-1" class="popup-box mfp-fade mfp-hide">
										<div class="content">
											<div class="image">
												<img src="images/wwork4.jpg" alt="">
											</div>
											<div class="desc">
												<div class="post-box">
													<h1>Blue Book of Recipes</h1>						
													<div class="blog-detail">Design</div>
													<div class="blog-content">
														<p>
															So striking at of to welcomed resolved. Northward by described up household therefore 
															attention. Excellence decisively nay man yet impression for contrasted remarkably.
														</p>
														<p>
															Forfeited you engrossed but gay sometimes explained. Another as studied it to evident. 
															Merry sense given he be arise. Conduct at an replied removal an amongst. Remaining 
															determine few her two cordially admitting old.
														</p>
														<blockquote>
															Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia 
															Curae; Pellentesque suscipit.
														</blockquote>
														<p>
															Tiled say decay spoil now walls meant house. My mr interest thoughts screened of outweigh 
															removing. Evening society musical besides inhabit ye my. Lose hill well up will he over on. 
															Increasing sufficient everything men him admiration unpleasing sex.
														</p>
														<ul class="list-style">
															<li>Greatest properly off ham exercise all.</li>
															<li>Unsatiable invitation its possession nor off.</li>
															<li>All difficulty estimating unreserved increasing the solicitude.</li>
														</ul>
														<p>
															Unpleasant astonished an diminution up partiality. Noisy an their of meant. Death means 
															up civil do an offer wound of.
														</p>
													</div>
													<a href="#" class="button">
														<span class="text">View Project</span>
														<span class="arrow"></span>
													</a>
												</div>
											</div>
										</div>
									</div>
								</div>
							</div>

							<!-- work item photo -->
							<div class="col col-d-6 col-t-6 col-m-12 grid-item gallery border-line-h">
								<div class="box-item">
									<div class="image">
										<a href="#gallery-1" class="has-popup-gallery">
											<img src="images/wwork5.jpg" alt="" />
											<span class="info">
												<span class="ion ion-images"></span>
											</span>
										</a>
										<div id="gallery-1" class="mfp-hide">
											<a href="images/wwork6.jpg"></a>
											<a href="images/wwork1.jpg"></a>
											<a href="images/wwork5.jpg"></a>
										</div>
									</div>
									<div class="desc">
										<a href="#gallery-1" class="name has-popup-gallery">Gereal Travels Book</a>
										<div class="category">Gallery</div>
									</div>
								</div>
							</div>

							<!-- work item music -->
							<div class="col col-d-6 col-t-6 col-m-12 grid-item music border-line-h">
								<div class="box-item">
									<div class="image">
										<a href="https://w.soundcloud.com/player/?visual=true&url=http%3A%2F%2Fapi.soundcloud.com%2Ftracks%2F221650664&show_artwork=true" class="has-popup-music">
											<img src="images/wwork6.jpg" alt="" />
											<span class="info">
												<span class="ion ion-music-note"></span>
											</span>
										</a>
									</div>
									<div class="desc">
										<a href="#" class="name has-popup">Daylight Entrance Book</a>
										<div class="category">Music</div>
									</div>
								</div>
							</div>

							<div class="clear"></div>
						</div>

					</div>

				</div>
			</div>

			<!--
				Card - Blog
			-->
			<div class="card-inner blog" id="blog-card"  v-if="false">
				<div class="card-wrap">

					<!-- Blog -->
					<div class="content blog">

						<!-- title -->
						<div class="title">
							<span >Blog</span>
						</div>

						<!-- content -->
						<div class="row border-line-v">
							<!-- blog item -->
							<div class="col col-d-6 col-t-6 col-m-12">
								<div class="box-item">
									<div class="image">
										<a href="blog-post-new.html">
											<img src="images/blog/blog1.jpg" alt="By spite about do of allow" />
											<span class="info">
												<span class="ion ion-document-text"></span>
											</span>
										</a>
									</div>
									<div class="desc">
										<a href="blog-post-new.html">
											<span class="date">April 28, 2020</span>
										</a>
										<a href="blog-post-new.html" class="name">By spite about do of allow</a>
										<div class="text">
											<p>Ex audire suavitate has, ei quodsi tacimates sapientem sed, pri zril ubique ut. Te cule tation munere noluisse. Enim torquatos&#8230;</p>
										</div>
									</div>
								</div>
							</div>
							<!-- blog item -->
							<div class="col col-d-6 col-t-6 col-m-12">
								<div class="box-item">
									<div class="image">
										<a href="blog-post-new.html">
											<img src="images/blog/blog2.jpg" alt="By spite about do of allow" />
											<span class="info">
												<span class="ion ion-document-text"></span>
											</span>
										</a>
									</div>
									<div class="desc">
										<a href="blog-post-new.html">
											<span class="date">April 28, 2020</span>
										</a>
										<a href="blog-post-new.html" class="name">By spite about do of allow</a>
										<div class="text">
											<p>Ex audire suavitate has, ei quodsi tacimates sapientem sed, pri zril ubique ut. Te cule tation munere noluisse. Enim torquatos&#8230;</p>
										</div>
									</div>
								</div>
							</div>
							<!-- blog item -->
							<div class="col col-d-6 col-t-6 col-m-12">
								<div class="box-item">
									<div class="image">
										<a href="blog-post-new.html">
											<img src="images/blog/blog3.jpg" alt="By spite about do of allow" />
											<span class="info">
												<span class="ion ion-document-text"></span>
											</span>
										</a>
									</div>
									<div class="desc">
										<a href="blog-post-new.html">
											<span class="date">April 28, 2020</span>
										</a>
										<a href="blog-post-new.html" class="name">By spite about do of allow</a>
										<div class="text">
											<p>Ex audire suavitate has, ei quodsi tacimates sapientem sed, pri zril ubique ut. Te cule tation munere noluisse. Enim torquatos&#8230;</p>
										</div>
									</div>
								</div>
							</div>
							<!-- blog item -->
							<div class="col col-d-6 col-t-6 col-m-12">
								<div class="box-item">
									<div class="image">
										<a href="blog-post-new.html">
											<img src="images/blog/blog1.jpg" alt="By spite about do of allow" />
											<span class="info">
												<span class="ion ion-document-text"></span>
											</span>
										</a>
									</div>
									<div class="desc">
										<a href="blog-post-new.html">
											<span class="date">April 28, 2020</span>
										</a>
										<a href="blog-post-new.html" class="name">By spite about do of allow</a>
										<div class="text">
											<p>Ex audire suavitate has, ei quodsi tacimates sapientem sed, pri zril ubique ut. Te cule tation munere noluisse. Enim torquatos&#8230;</p>
										</div>
									</div>
								</div>
							</div>
							<div class="clear"></div>
						</div>

						<div class="pager">
							<nav class="navigation pagination">
								<div class="nav-links">
									<span class="page-numbers current">1</span>
									<a class="page-numbers" href="#">2</a>
									<a class="next page-numbers" href="#">Next</a>
								</div>
							</nav>
						</div>

					</div>

				</div>
			</div>

			<!--
				Card - Contacts
			-->
			<div class="card-inner contacts" id="contacts-card">
				<div class="card-wrap">

					<!--
						Conacts Info
					-->
					<div class="content contacts">

						<!-- title -->
						<div class="title">Get in Touch</div>

						<!-- content -->
						<div class="row">
							<div class="col col-d-12 col-t-12 col-m-12 border-line-v">
								<div class="map" id="map"></div>
								<div class="info-list">
									<ul>
										<li style="display: block !important;"><strong>Address . . .</strong> {{profile.address}}, {{profile.county}}</li>
										<li style="display: block !important;"><strong>Email . . .</strong> {{profile.mail}}</li>
										<li style="display: block !important;"><strong>Phone . . .</strong> {{profile.tel}}</li>
										<li style="display: block !important;"><strong>Line . . .</strong> {{profile.line}}</li>
										<li style="display: block !important;"><strong>Freelance . . .</strong> {{profile.freelance}}</li>
									</ul>
								</div>
							</div>
							<div class="clear"></div>
						</div>

					</div>

					<!--
						Contact Form
					-->
					<div class="content contacts" v-if="false">

						<!-- title -->
						<div class="title">Contact Form</div>

						<!-- content -->
						<div class="row">
							<div class="col col-d-12 col-t-12 col-m-12 border-line-v">
								<div class="contact_form">
									<form id="cform" method="post">
										<div class="row">
											<div class="col col-d-6 col-t-6 col-m-12">
												<div class="group-val">
													<input type="text" name="name" placeholder="Full Name" />
												</div>
											</div>
											<div class="col col-d-6 col-t-6 col-m-12">
												<div class="group-val">
													<input type="text" name="email" placeholder="Email Address" />
												</div>
											</div>
											<div class="col col-d-12 col-t-12 col-m-12">
												<div class="group-val">
													<textarea name="message" placeholder="Your Message"></textarea>
												</div>
											</div>
										</div>
										<div class="align-left">
											<a href="#" class="button" onclick="$('#cform').submit(); return false;">
												<span class="text">Send Message</span>
												<span class="arrow"></span>
											</a>
										</div>
									</form>
									<div class="alert-success">
										<p>Thanks, your message is sent successfully.</p>
									</div>
								</div>
							</div>
							<div class="clear"></div>
						</div>

					</div>

				</div>
			</div>

		</div>

		<div class="s_overlay"></div>
		<div class="content-sidebar">
			<div class="sidebar-wrap search-form">
				<aside id="secondary" class="widget-area">
					<section id="search-2" class="widget widget_search">
						<label>
							<span class="screen-reader-text">Search for:</span>
							<input type="search" class="search-field" placeholder="Search …" value="" name="s">
						</label>
						<input type="submit" class="search-submit" value="Search">
					</section>
					<section class="widget widget_recent_entries">
						<h2 class="widget-title">
							<span class="widget-title-span"><span class="first-word">Recent</span> Posts</span>
						</h2>
						<ul>
							<li>
								<a href="#">Creativity Is More Than</a>
							</li>
							<li>
								<a href="#">Designing the perfect</a>
							</li>
							<li>
								<a href="#">Music Player Design</a>
							</li>
							<li>
								<a href="#">A Song And Dance Act</a>
							</li>
							<li>
								<a href="#">By spite about do of allow</a>
							</li>
						</ul>
					</section>
					<section class="widget widget_recent_comments">
						<h2 class="widget-title">
							<span class="widget-title-span"><span class="first-word">Recent</span> Comments</span>
						</h2>
						<ul>
							<li class="recentcomments">
								<span class="comment-author-link">JOHN SMITH</span> on <a href="#">Creativity Is More Than</a>
							</li>
							<li class="recentcomments">
								<span class="comment-author-link">ADAM SMITH</span> on <a href="#">Creativity Is More Than</a>
							</li>
							<li class="recentcomments">
								<span class="comment-author-link">admin</span> on <a href="#">Designing the perfect</a>
							</li>
							<li class="recentcomments">
								<span class="comment-author-link">admin</span> on <a href="#">Designing the perfect</a>
							</li>
							<li class="recentcomments">
								<span class="comment-author-link">James</span> on <a href="#">Designing the perfect</a>
							</li>
						</ul>
					</section>
					<section class="widget widget_archive">
						<h2 class="widget-title">
							<span class="widget-title-span">
								<span class="first-letter">Archives</span>
							</span>
						</h2>
						<ul>
							<li>
								<a href="#">November 2018</a>
							</li>
						</ul>
					</section>
					<section class="widget widget_categories">
						<h2 class="widget-title">
							<span class="widget-title-span"><span class="first-letter">Categories</span></span>
						</h2>
						<ul>
							<li class="cat-item cat-item-2">
								<a href="#">Design</a>
							</li>
							<li class="cat-item cat-item-3">
								<a href="#">Music</a>
							</li>
						</ul>
					</section>
					<section class="widget widget_meta">
						<h2 class="widget-title">
							<span class="widget-title-span"><span class="first-letter">Meta</span></span>
						</h2>
						<ul>
							<li><a href="#">Log in</a></li>
							<li><a href="#">Entries feed</a></li>
							<li><a href="#">Comments feed</a></li>
							<li><a href="#">WordPress.org</a></li>
						</ul>
					</section>
				</aside>
			</div>
			<span class="close"></span>
		</div>

	</div>
</template>

<script>
import profile from './profile'
export default {
    name: 'App',
    components: {
    },
    data() {
        return {
            profile: profile
        }
    },
    computed: {
        birthYear: function () {
            return new Date().getFullYear() - this.profile.birthyear
        }
    },
}
</script>

<style>
.content.contacts .info-list ul li {
    padding: 11px 30px;
    display: inline-block;
    vertical-align: top;
    width: 100%;
}

.info-list ul li {
    padding: 0 0 5px 0;
    display: inline-block;
    vertical-align: top;
    width: 100%;
    text-align: left;
}
</style>
