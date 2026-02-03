<script>
	import './layout.css';
</script>

<main>
	<section>
		<!-- @todo Canvas with animation as bg -->
		<div>
			<figure>
				<!-- @todo Hide image on mobile, only show figcaption & bg -->
				<img
					src="https://assets.mvc.ink/f/1020547/1249x694/4189936aab/jaroslaw-marcinek-2209-40.jpg/m/"
					alt="Illustration by Jaroslaw Marcinek"
				/>

				<figcaption>
					<p>BETA READERS NEEDED</p>
				</figcaption>
			</figure>
		</div>
	</section>

	<section>
		<div>
			<h1>
				<span>Fragile Gamete</span>
				<br />
				<span>of Resistance</span>
			</h1>

			<p>by <span>Michael V. Colianna</span> (he/xe)</p>

			<div>
				<!-- @todo Make these a component -->
				<div>
					<!-- @todo Genre icon -->
					<span>Adult Sci-Fi</span>
				</div>

				<div>
					<!-- @todo Wordcount icon -->
					<span>110k words</span>
				</div>

				<div>
					<!-- @todo Read time icon -->
					<span>~9 hours</span>
				</div>

				<div>
					<!-- @todo Timeline icon -->
					<span>End of March</span>
				</div>
			</div>
		</div>
	</section>

	<section>
		<div>
			<div>
				<div>
					<p>
						If you’d asked Mary and Davi how things were going a month ago, it would have been rave
						reviews. Co-captains of a smuggling ship, they’d stumbled upon a universe-wide
						conspiracy – but they convinced their friends to fight back. Even though they lost a
						bunch of money, got robbed, and compromised their morals a little, things were back on
						track. Finally, they could start their first IVF cycle and maybe take a break, right? <em
							>Not so fast…</em
						>
					</p>

					<p>
						Despite a good start, Mary and Davi’s IVF cycle failed. On top of that, their friends
						are struggling to fight the Gaians. Those are the human-appearing aliens behind the plot
						to take over the Three Empires and oppress humanity. They seem to have already adjusted
						and are always several steps ahead. So Mary and Davi will have to put their dreams on
						hold <em>once again</em> to help out.
					</p>

					<p>
						But there seems to be no end to the bad news. Mary and Davi keep getting hit while they
						are down. Nobody else wants to stand up and fight back. And that’s before they have a
						huge fight. Everyone has a limit, and the stress is causing them to take it out on one
						another – as well as on themselves. Defeating the Gaians will bring them both to the
						breaking point, <strong>and neither is confident they’ll hold strong</strong>.
					</p>
				</div>

				<details>
					<summary>
						<span>Content Warnings</span>
						<!-- @todo Chevron down icon -->
					</summary>

					<div>
						<ul>
							<!-- @todo Make these a component -->
							<li>
								<span>•</span>
								<span>Fertility difficulties</span>
							</li>

							<li>
								<span>•</span>
								<span>Suicidal ideation and mentions</span>
							</li>

							<li>
								<span>•</span>
								<span>Mentions of miscarriage</span>
							</li>

							<li>
								<span>•</span>
								<span>Mentions of attempted sexual assault</span>
							</li>

							<li>
								<span>•</span>
								<span>Violence, death, alcohol use, and language</span>
							</li>
						</ul>
					</div>
				</details>
			</div>
		</div>
	</section>

	<section>
		<div>
			<h2>Connect with MVC</h2>

			<p>Get in contact to read, or use the form below.</p>

			<div>
				<!-- @todo Make these a component -->
				<a href="/">
					<!-- @todo Bluesky icon -->
					<span>Connect on Bluesky</span>
				</a>

				<a href="/">
					<!-- @todo Discord icon -->
					<span>Connect on Discord</span>
				</a>

				<a href="/">
					<!-- @todo Web icon -->
					<span>Visit MVC's Website</span>
				</a>

				<a href="/">
					<!-- @todo Email icon -->
					<span>Send MVC an Email</span>
				</a>
			</div>
		</div>
	</section>

	<section>
		<div>
			<div>
				<div>
					<h2>Sign up to Beta Read</h2>

					<p>Interested in being a beta reader? Fill out the form below.</p>
				</div>

				<!-- @todo Netlify formify -->
				<form>
					<!-- @todo Make text/email fields a component -->
					<div>
						<label for="name">Name <span aria-label="(Required)">*</span></label>

						<input id="name" type="text" placeholder="Your name" required />
					</div>

					<div>
						<label for="email">Email <span aria-label="(Required)">*</span></label>

						<input id="email" type="email" placeholder="you@example.com" required />
					</div>

					<div>
						<label for="pronouns">Pronouns</label>

						<input id="pronouns" type="text" placeholder="e.g., she/her, they/them (Optional)" />
					</div>

					<div>
						<div>
							Preferred Way To Read &amp; Comment <span aria-label="(Required)">*</span>
						</div>

						<div role="radiogroup" aria-required="true">
							<label>
								<button
									type="button"
									role="radio"
									aria-checked="false"
									aria-label="Google Docs"
									value="gdocs"
									id="delivery-gdocs"
								></button>
								<input type="radio" aria-hidden="true" required value="gdocs" />
								<span>Google Docs</span>
							</label>

							<label>
								<button
									type="button"
									role="radio"
									aria-checked="false"
									aria-label="PDF"
									value="pdf"
									id="delivery-pdf"
								></button>
								<input type="radio" aria-hidden="true" required value="pdf" />
								<span>PDF</span>
							</label>

							<label>
								<button
									type="button"
									role="radio"
									aria-checked="false"
									aria-label="Word Doc"
									value="word"
									id="delivery-word"
								></button>
								<input type="radio" aria-hidden="true" required value="word" />
								<span>Word Doc</span>
							</label>
						</div>
					</div>

					<div>
						<label for="about">What made you want to read?</label>

						<textarea
							id="about"
							placeholder="Are you a reviewer, blogger, or just a sci-fi enthusiast? Tell me a bit about yourself! (Optional)"
							rows="4"
						></textarea>
					</div>

					<p>
						<a href="#privacy">Concerned about privacy?</a>
					</p>

					<button type="submit">
						<!-- @todo Submit icon -->
						Submit Request
					</button>
				</form>
			</div>
		</div>
	</section>

	<section>
		<div>
			<div>
				<h2>Praise &amp: Reactions</h2>

				<p>
					Some things others readers have said about their beta read, or about MVC’s first book, <a
						href="/">Fractured Children or Earth</a
					>.
				</p>
			</div>

			<div>
				<!-- @todo Make these a component -->
				<article>
					<!-- @todo Quote icon -->

					<blockquote>
						You’re a very good writer, but this was way too woke for me to read.
					</blockquote>

					<footer>
						<div>
							<cite>Creigh Maxfield</cite>

							<p>About <em>Fractured Children of Earth</em></p>
						</div>
					</footer>
				</article>

				<article>
					<!-- @todo Quote icon -->

					<blockquote>
						MVC writes with the wonder of Chambers and the heart of Le Guin. This is science fiction
						at its finest.
					</blockquote>

					<footer>
						<div>
							<cite>K.A. Doore</cite>

							<p>For <em>Fractured Children of Earth</em></p>
						</div>
					</footer>
				</article>

				<article>
					<!-- @todo Quote icon -->

					<blockquote>
						Holy crap, man. Are you okay? Because that ending really worries me.
					</blockquote>

					<footer>
						<div>
							<cite>@juliebihn.bsky.social</cite>

							<p>For <em>Fragile Gamete of Resistance</em></p>
						</div>
					</footer>
				</article>

				<article>
					<!-- @todo Quote icon -->

					<blockquote>
						When I tell you that I cried my eyes out, please know that very few books have ever done
						that. I’ve got a very high tolerance for grief and sadness. Your story will haunt me for
						months, and I can't wait to see it published.
					</blockquote>

					<footer>
						<div>
							<cite>bookish_nova (Discord)</cite>

							<p>For <em>Fragile Gamete of Resistance</em></p>
						</div>
					</footer>
				</article>
			</div>
		</div>
	</section>

	<section>
		<div>
			<div>
				<div>
					<div>
						<h2>Sample</h2>

						<p>From Chapter Four, <em>Every Tear That Softly Stains</em></p>
					</div>
				</div>

				<div>
					<!-- @todo Expanded/contracted states -->
					<article>
						<p>
							This discussion suddenly reminded Davi of the coffee contract fight that made the five
							members of the Vinillense quit. As well, it drew some similarity to his argument with
							Mary where she almost hit him. Anger clouded his judgment both times, and though
							Puccar’s stubborn refusal to help burned him like a grenade bolt, he somehow wrangled
							his emotions.
						</p>

						<p>
							“Just so I understand: You yourself said that his plan is to take us over and absorb
							our culture, and that you don’t want that. You agree that Ganmel needs to be stopped.
							But instead of taking direct action against him, you’re willing to wait and see if you
							can legislate him away? Do I have that right?” Davi asked, barely keeping himself
							under control.
						</p>

						<p>
							Puccar waved his hand in dismissal, then signed back, “I understand that you think
							this is more urgent than it really is, but I think you’re overreacting. We have plenty
							of time to stop him the right way.”
						</p>

						<p>
							Mary clenched her fists in response to that and Davi put his hand on her back in
							support. To Puccar, he said, “We have a device that blocks dielsis. It blocks the
							power and alerts us of the attempt. The Cartel has already held several meetings with
							some cities, using those devices. We’ve made no headway. Nobody believes us. Yet we
							are at the nine year mark that Ganmel set for the final stage of his plan. So forgive
							us when we say it’s pretty fucking urgent.”
						</p>

						<p>This didn’t sway Puccar. “And I’m telling you we will handle him.”</p>
					</article>

					<!-- @todo Gradient overlay when contracted -->
				</div>

				<div>
					<button type="button">
						<!-- @todo Different text for state -->
						<span>Show Less/Continue Reading</span>

						<!-- @todo Chevron icon, rotate for state -->
					</button>
				</div>
			</div>
		</div>
	</section>

	<footer id="privacy">
		<div>
			<div>
				<h3>Privacy Policy</h3>

				<div>
					<p>
						Your privacy matters. Information submitted through this site is used solely by MVC to
						communicate directly with you about this book. Your data is never saved to any
						third-party database, sold, shared, or used for marketing purposes.
					</p>

					<p>
						Once your request is fulfilled, your information will be deleted unless you explicitly
						opt in to future updates. By submitting the form, you consent to receiving direct
						communication from MVC regarding your advance reader copy request.
					</p>
				</div>

				<div>
					<p>© 2026 MVC. All rights reserved.</p>
				</div>
			</div>
		</div>
	</footer>
</main>
