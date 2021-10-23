<template>
	<div>
		<CBox
			pl="4rem"
			pr="4rem"
			pt="3rem"
			d="flex"
			v-bind="mainStyles[colorMode]"
			flex-direction="column"
		>
			<CHeading as="h3" size="lg" pb="1rem">Monthly Stories from the Game World</CHeading>

			<CBox d="flex" pb="2.2rem" class="dash-container">
				<div class="dash-one"></div>
				<div class="dash-two"></div>
			</CBox>

			<CBox
				
				borderBottom="1px solid #E8E8E8;"
				v-for="(item, index) in items"
				:key="item.content_id"
				mb="1rem"
			>
				<CBox class="date-container">
					<CText fontSize="l" font-weight="bold">
						{{
							new Date(item.created_at).toLocaleString("default", {
								month: "long",
								year: "numeric",
								day: "numeric"
							})
						}}
					</CText>
				</CBox>
				<CBox d="flex" align-items="flex-start" justify-content="space-between">
					<CText pr="2rem" pt="1rem" pb="1rem"> {{ item.content }}. </CText>
					<div>
						<span class="new-item" v-if="index < 2">NEW</span>
					</div>
				</CBox>
			</CBox>

			<CBox d="flex" justify-content="flex-end" v-if="this.items > 0">
				<CBox as="a" href="#" >
					<CText font-weight="bold" color="#C5283D" pb="2rem">
						VIEW ALL
					</CText>
				</CBox>
			</CBox>
		</CBox>



		
	</div>
</template>

<script>
import { CBox, CPseudoBox, CHeading, CText, CDivider } from "@chakra-ui/vue";

export default {
	name:'notifications',

	inject: ["$chakraColorMode", "$toggleColorMode"],

	computed: {
		toggleColorMode() {
			return this.$toggleColorMode;
		},

		colorMode() {
			return this.$chakraColorMode();
		}
	},
	components: {
		CBox,
		CPseudoBox,
		CHeading,
		CText,
		CDivider
	},

	data() {
		return {
			items: [],

			monthsMarker: {
				January: 0,
				February: 0,
				March: 0,
				April: 0,
				May: 0,
				June: 0,
				July: 0,
				August: 0,
				September: 0,
				October: 0,
				November: 0,
				December: 0
			},

			mainStyles: {
				dark: {
					bg: "gray.700",
					color: "whiteAlpha.900"
				},
				light: {
					bg: "white",
					color: "gray.900"
				}
			}
		};
	},

	async fetch() {
		console.log(this);
		// const data = await this.$axios.get(
		// 	`http://localhost:8000/api/getnotification/?ps=4`

		// );

		const data = {     "count": 1,     "next": null,     "previous": null,     "results": [          {             "option_info": "",             "content_id": "21259240-4r43-4dfa-937f-4112ef43c694",             "content": "This is a dummy notification which is the replica of the server data structure",             "file_pdf": "http://localhost:8000/media/notification/NH2402079449920_Wvqg6tL.pdf",             "created_at": "2021-09-30T10:28:44.051394+05:30",             "updated_at": "2021-09-30T10:28:44.051424+05:30"         },          {             "option_info": "",             "content_id": "21259240-4r43-4dfa-937f-4112ef43c694",             "content": "I’ll invite you to read this slowly. To remember that a voice is embodied in this text, that in this process of following the sentence towards its meaning, in a kind of walking, as in a procession or parade, the writer’s creative process will emerge, a deliberate motion with care as the foundation for which the writer is then able to articulate beauty and suggest some new knowledge, but of course, this will take time.",             "file_pdf": "http://localhost:8000/media/notification/NH2402079449920_Wvqg6tL.pdf",             "created_at": "2021-09-30T10:28:44.051394+05:30",             "updated_at": "2021-09-30T10:28:44.051424+05:30"         },          {             "option_info": "",             "content_id": "21259240-4r43-4dfa-937f-4112ef43c694",             "content": "Let me suggest lichen, for example. To illustrate what I mean by slow. I was struck one day when I was walking and listening to a lichenologist, Kerry Knudsen, propose that lichen was the ultimate resistor to capitalism. Lichen can grow over millions of years, he says, that in the southwestern Mojave Desert, some lichen matures so slowly that some only grow a fraction of an inch per year. From this, he advocates, we should learn how to slow down, urging that this slow growth can help us to see our own position more clearly. To become aware of ourselves. That lichen can’t reproduce quickly makes them even more precious, singular.",             "file_pdf": "http://localhost:8000/media/notification/abc.pdf",             "created_at": "2021-09-30T10:28:44.051394+05:30",             "updated_at": "2021-09-30T10:28:44.051424+05:30"         },          {             "option_info": "",             "content_id": "21259240-4r43-4dfa-937f-4112ef43c694",             "content": "Of lichen Mary Ruefle wrote that lichen is so old, “among the oldest living things on earth” that we should give them “considerable respect” and while old and slow are two different things, I think we can say that respect is an earned pronouncement for both. The poet Jane Hirshfield has written that lichens are “transformers unvalued, uncounted. Cell by cell, word by word, making a world they could live in.” So, lichen as the ultimate dissident, quite adaptable and creative, incredibly patient and generally okay with how long it takes to do things",             "file_pdf": "http://localhost:8000/media/notification/abc.pdf",             "created_at": "2021-09-30T10:28:44.051394+05:30",             "updated_at": "2021-09-30T10:28:44.051424+05:30"         },          {             "option_info": "",             "content_id": "21259240-4r43-4dfa-937f-4112ef43c694",             "content": "We should lichenize our writing. And in this, I mean, challenge all the ways we are influenced to rush our composition, to push against capitalism’s engine insisting a kind of efficient production of creative works. Instead, how can we, as writers, contest the urge to produce at real or imagined external timelines",             "file_pdf": "http://localhost:8000/media/notification/abc.pdf",             "created_at": "2021-09-30T10:28:44.051394+05:30",             "updated_at": "2021-09-30T10:28:44.051424+05:30"         },          {             "option_info": "",             "content_id": "21259240-4r43-4dfa-937f-4112ef43c694",             "content": "The OED’s definition of slow suggests a lack of liveliness, deficient in momentum, characterized by sloth, absent of mental acuity, teeming with reluctance and delay, not of the times, dull, without passion and without rouse. This is not helpful in relationship to creative works. It is only toward the bottom where some of the shorter, more nuanced entries in the OED appear and where one encounters fewer negative connotations of slow—the deliberate action, as matched with care and softness. With music, in tempo, related to sensuality. Of something gentle, like fire, from RH Dana in 1840, “We made a slow fire of charcoal, birch bark, brimstone, and other matters.”",             "file_pdf": "http://localhost:8000/media/notification/abc.pdf",             "created_at": "2021-09-30T10:28:44.051394+05:30",             "updated_at": "2021-09-30T10:28:44.051424+05:30"         },                           {             "option_info": "",             "content_id": "21259240-4r43-4dfa-937f-4112ef43c694",             "content": "All things good, slow means listening. To allow the inner self to hear what ideas may generate from words placed on a page. I have been writing an essay on vanity, masks, photography, and self-image for over two years and in this slow process, I continually witness new possibilities in listening for these themes as they emerge within my life structures. As an observer of my own life, a documentarian of experience, the painting of a woman seen on social media might suggest a new angle on how women’s bodies are represented in art, might influence the ending of my essay, which has yet to emerge. Or perhaps a dream is remembered, a conversation takes place between myself and a friend in which we consider an aspect of performance in photography—anything in this recognition might lend itself to my slow writing. When will the essay be done? I cannot say, though I am committed to the slow maturity of its final telling.  To allow myself this pace, I discover a tension between freedom and impatience, that is, in the slow, I find a fresh inventiveness and sovereignty from the relentless influence of our economic system. Though within this, I must temper and unlearn my own fixed haste at generating creative work at a rapid measure. I hear an internal voice telling me, write faster, go faster, you’re not doing it right, and it takes might and fortitude to reject this voice obsessed with speed. If I can suggest a slower methodology, then the practice is that of contemplation, deliberate reflection, slow thought, which results in intricate language, in a new kind of assembly as evidenced by the messiness of my hard drive, notebooks, diaries, and iPhone notes apps, of which there are many. I prefer the reprieve of the slow. I like writing more when performed at an adagio. It’s a relief. A sanctuary. Even as I write this, I have no deadline, a freedom as such, an open-ended time frame, which allows for me to convene with my ideas.  There’s also something to be said about collating and curating in the slow writing process—facts, knowledge, smells, descriptions, stories, passport stamps, headlines—until the collection becomes part of the transformation process. Through acute and critical attention, away from the drive of production, toward the singularity of studying a branch, rock, story, glance, gesture, word history, repetition, the slow writing process takes control of time and becomes a reclamation act, creating space on which thought and process flourishes, allowing for curiosity to direct you forward. There’s a physicality to it. Muscles loosen.  At the same time, it’s uncomfortable to be slow. We do not like the slow car, the slow human, the slow traffic, the slow Wi-Fi, the lady in line searching for change in her wallet, the person taking too long in the bathroom, the snail, though I do love the wicked beauty of the exoskeleton spiraling, whorls that add with age, all pointing toward a small aperture at the end of the last twist. We would do well to learn from snails. They move at their own pace by pedal waves, their muscles tightening to scoot forward. They slipstream through gardens at night following their fellow snails through the slime onto their next destination. And their favorite food is lichen.  Slow writing is not without delight. Slow writing is passionate engagement, an intensified focus, a process that nurtures the creative artist. The slow (now having become its own subject, like the snail, lichen) and the artist become a synergy that motions for a type of repeated homecoming. It’s almost something of an obsession. Come back for more. You know you want to. Michelle Boulous Walker, in her book, Slow Philosophy, equates the slow as a beginning way of thinking toward complexity, a passion with the world that can determine a kind of responsibility. Walker argues for a kind of dwelling in order to innovate. To inhabit a slow writing framework, then, is to originate a kind of revolution in creativity.",             "file_pdf": "http://localhost:8000/media/notification/abc.pdf",             "created_at": "2021-09-30T10:28:44.051394+05:30",             "updated_at": "2021-09-30T10:28:44.051424+05:30"         }         ] }

		this.items = data.results;
	},

	methods: {
		// assignNewByUTC(created_at){

		//     const x = new Date(created_at)
		//     x = x.getMonth() + ", "+ x.getYear()

		//     return x

		// }

		async monthSetup(created_at, index) {
			const bool = null;

			if (process.client) {
				const x = new Date(created_at).toLocaleString("default", { month: "long" });

				console.log("ON CLIENT CSR");
				console.log(this.monthsMarker[x]);
				if (this.monthsMarker[x] == 0) {
					this.monthsMarker[x] = 1;
				}

				// TODO : Conditional stuff not working yet
			}
			if (process.server) {
				console.log("ON SERVER SSR");
				return false;
			}
		}
	}
};
</script>

<style></style>
