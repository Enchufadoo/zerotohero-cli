<template>
  <div>
    <div class="jumbotron-fluid p-5 bg-white mb-0" style="overflow: hidden; position: relative">
      <div class="container">
        <div class="row">
          <div class="col-md-3"></div>
          <div class="col-sm-12 col-md-6">
            <YouTubeVideo youtube="5tCCX95G2vg" class="shadow" style="z-index: 2" />
          </div>
          <div class="col-md-3"></div>
        </div>
      </div>
      <img src="img/ken-standing.png" alt="Ken" class="photo-ken d-none d-md-block" />
      <img src="img/jon-sitting.png" alt="Jon" class="photo-jon d-none d-md-block" />
    </div>
    <!-- <Sale /> -->
    <div class="jumbotron-fluid bg-dark p-5 text-light mb-0 courses" style="position: relative">
      <div class="container text-center foreground">
        <h3 class="mb-4">Online Chinese Courses at All Levels</h3>
        <p>
          We provide online Chinese courses at all levels, from
          <a
            href="http://chinesezerotohero.teachable.com"
            style="color: white; font-weight: bold;"
          >HSK 1 to HSK 6</a>.
        </p>
        <p>
          If you don't know what HSK is, check this
          <a
            href="https://en.wikipedia.org/wiki/Hanyu_Shuiping_Kaoshi"
            target="_blank"
            style="color: white; font-weight: bold;"
          >Wikipedia article</a>.
        </p>
        <a
          href="https://chinesezerotohero.teachable.com/"
          class="btn btn-danger mt-3 mb-2"
        >Browse All Courses</a>
      </div>
    </div>
    <div class="jumbotron-fluid mb-0 pb-0 pt-0">
      <div class="container">
        <h3 class="pb-5 pt-5 text-center">Get Our Latest Content</h3>
        <div class="row">
          <div class="col-md-6 col-lg-4 mb-5">
            <h5 class="mb-4 text-center">Instagram</h5>
            <a href="https://www.instagram.com/chinesezerotohero/" class="text-center">
              <span class="media">
                <img src="img/logo-zh-zth-circle.png" style="width: 4rem" />
                <div class="media-body">
                  instagram.com/
                  <b>chinesezerotohero</b>
                </div>
              </span>
            </a>
            <p>
              We regularly post "word of the day" images and grammar poster
              images. Get your daily dose of Chinese by following our Instagram
              account. We regularly upload grammar and vocabulary videos on IGTV
              as well.
            </p>
          </div>
          <div class="col-md-6 col-lg-4 mb-5">
            <h5 class="mb-4 text-center">Reddit</h5>
            <a href="https://www.reddit.com/user/chinesezerotohero" class="text-center">
              <span class="media">
                <img src="img/logo-zh-zth-circle.png" style="width: 4rem" />
                <div class="media-body">
                  reddit.com/u/
                  <b>ChineseZeroToHero</b>
                </div>
              </span>
            </a>
            <p>
              Jon is
              <a
                href="https://www.reddit.com/user/ChineseZeroToHero/submitted/"
              >u/ChineseZeroToHero</a>
              on Reddit. He regularly posts Chinese-learning resources and
              observations about Chinese language and grammar at
              r/ChineseLanguage.
            </p>
            <p>
              We encourage you to follow Jon at
              <a
                href="https://www.reddit.com/user/ChineseZeroToHero/submitted/"
              >u/ChineseZeroToHero</a>, and also monitor
              <a
                href="https://www.reddit.com/r/ChineseLanguage/"
              >r/ChineseLanguage</a>
              for the latest Chinese-learning content from across the web.
            </p>
          </div>
          <div class="col-md-6 col-lg-4 mb-5">
            <h5 class="mb-4 text-center">YouTube</h5>
            <a href="https://www.youtube.com/chinesezerotohero" class="text-center">
              <span class="media">
                <img src="img/logo-zh-zth-circle.png" style="width: 4rem" />
                <div class="media-body">
                  youtube.com/
                  <b>chinesezerotohero</b>
                </div>
              </span>
            </a>
            <p>
              We regularly post Chinese-learning videos to YouTube. We also
              provide frequent announcements regarding new course feature,
              promotional events, and such. In the comment area, you can also
              connect with other learners.
            </p>
            <p>
              Because we post a lot of content that is not found in our courses,
              we recommend that you follow us even if you've already bought all
              of our courses.
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="container mt-5 mb-5">
    <div class="row">
      <div class="col-sm-12">
        <h1 class="mb-5 text-center">Courses that take your Chinese to the next level.</h1>
      </div>
    </div>
    <div class="row">
      <div class="col-sm-12">
        <div class="jumbotron text-center courses">
          <div class="container mb-3">
            <h3>Course Bundles</h3>
            <hr />
            <div class="row">
              <div class="col-sm-6 col-md-4 mb-3">
                <a
                  target="_blank"
                  :href="
                  `https://chinesezerotohero.teachable.com/p/ultimate-bundle`
                "
                >
                  <img
                    :src="`/img/courses/bundle-ultimate.jpg`"
                    alt="Ultimate Bundle"
                    class="img-fluid shadow rounded"
                  />
                  <h5 class="mt-2">
                    Ultimate HSK 1 - 6 Bundle
                    <i class="fa fa-external-link-alt small ml-1" />
                  </h5>
                </a>
              </div>
              <div class="col-sm-6 col-md-4 mb-3">
                <a
                  target="_blank"
                  :href="
                  `https://chinesezerotohero.teachable.com/p/hsk-1-4-bundle`
                "
                >
                  <img
                    :src="`/img/courses/bundle-hsk-1-4.jpg`"
                    alt="HSK 1 - 4 Bundle"
                    class="img-fluid shadow rounded"
                  />
                  <h5 class="mt-2">
                    HSK 1 - 4 Bundle
                    <i class="fa fa-external-link-alt small ml-1" />
                  </h5>
                </a>
              </div>
              <div class="col-sm-6 col-md-4 mb-3">
                <a
                  target="_blank"
                  :href="
                  `https://chinesezerotohero.teachable.com/p/hsk-5-6-bundle`
                "
                >
                  <img
                    :src="`/img/courses/bundle-hsk-5-6.jpg`"
                    alt="HSK 5 - 6 Bundle"
                    class="img-fluid shadow rounded"
                  />
                  <h5 class="mt-2">
                    HSK 5 - 6 Bundle
                    <i class="fa fa-external-link-alt small ml-1" />
                  </h5>
                </a>
              </div>
            </div>
            <h3>Individual Courses</h3>
            <hr />
            <div class="row">
              <div class="col-sm-6 col-md-4 mb-3" v-for="hsk in [1, 2, 3, 4, 5, 6]">
                <a
                  target="_blank"
                  :href="
                  `https://courses.chinesezerotohero.com/p/hsk-${hsk}-course`
                "
                >
                  <img
                    :src="`/img/courses/hsk${hsk}.jpg`"
                    :alt="`HSK ${hsk} Course`"
                    class="img-fluid shadow rounded"
                  />
                  <h5 class="mt-2">
                    HSK {{ hsk }} Course
                    <i class="fa fa-external-link-alt small ml-1" />
                  </h5>
                </a>
              </div>
              <div class="col-sm-6 col-md-4 mb-3">
                <a
                  target="_blank"
                  :href="
                  `https://chinesezerotohero.teachable.com/p/path-to-fluency`
                "
                >
                  <img
                    :src="`/img/courses/fluency.jpg`"
                    alt="Path to Fluency Course"
                    class="img-fluid shadow rounded"
                  />
                  <h5 class="mt-2">
                    Path to Fluency
                    <i class="fa fa-external-link-alt small ml-1" />
                  </h5>
                </a>
              </div>
            </div>
            <h3>Free Courses</h3>
            <hr />
            <div class="row">
              <div class="col-sm-6 col-md-4 mb-3">
                <a
                  target="_blank"
                  :href="
                  `https://chinesezerotohero.teachable.com/p/phonetics-with-chinese-characteristics`
                "
                >
                  <img
                    :src="`/img/courses/phonetics.jpg`"
                    alt="Phonetics with Chinese Characteristics"
                    class="img-fluid shadow rounded"
                  />
                  <h5 class="mt-2">
                    Phonetics with Chinese Characteristics
                    <i
                      class="fa fa-external-link-alt small ml-1"
                    />
                  </h5>
                </a>
              </div>
              <div class="col-sm-6 col-md-4 mb-3">
                <a
                  target="_blank"
                  :href="
                  `https://chinesezerotohero.teachable.com/p/ci-shifu-vocabulary-course`
                "
                >
                  <img
                    :src="`/img/courses/cishifu.jpg`"
                    alt="Ci Shifu Vocabulary Master"
                    class="img-fluid shadow rounded"
                  />
                  <h5 class="mt-2">
                    Ci Shifu Vocabulary Master
                    <i class="fa fa-external-link-alt small ml-1" />
                  </h5>
                </a>
              </div>
            </div>
          </div>
          <a
            href="https://chinesezerotohero.teachable.com/"
            class="btn btn-success view-courses pb-1 bigger"
            target="_blank"
          >
            View all of our courses and bundles on
            <img
              src="/img/teachable_light.png"
              alt="Teachable"
              class="logo-small mb-1"
            />
          </a>
          <p class="mt-3">
            <b>Teachable</b> is an online platform that hosts video courses.
          </p>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-sm-6">
        <h3 class="mb-3">What makes our courses different?</h3>
        <h5>Functional</h5>
        <p>
          You learn a language so you can do things with it – to accomplish
          real-world tasks, or functions. From day 1, we focus on enabling
          students to “do something” with what they learn, and design our
          lessons around that objective. We try to steer around overuse of
          unecessary jargons and lengthy explanations and focus on practical
          applications.
        </p>
        <h5>Engaging</h5>
        <p>
          <strong>
            Learning is hard work, but it should never be boring, so we
            designed our courses to be concise yet fun and engaging.
          </strong>
          &nbsp;We use instruction design principles proposed by
          <a
            href="https://en.wikipedia.org/wiki/Robert_M._Gagn%C3%A9"
            target="_blank"
          >Robert M. Gagné</a>, as well as multimedia learning guidelines by
          <a
            href="https://en.wikipedia.org/wiki/Richard_E._Mayer"
            target="_blank"
          >Richard E. Mayer</a>.&nbsp; The instructional designs are so successful that we have
          received many raving reviews from our students.
        </p>
        <h5>Communicative</h5>
        <p class>
          <strong>
            All of our
            <a href="https://courses.chinesezerotohero.com/courses/">courses</a>
            focus on communication and function
          </strong>. &nbsp;We strive to help students use the language by providing
          plenty of practice, both written and oral. &nbsp;We help and encourage
          students to practice with a language exchange partner via sites such
          as
          <a
            href="https://www.italki.com/"
          >iTalki</a>.&nbsp; This way
          students learn to use the language in real life, not just to pass
          tests.
        </p>
        <h5>Standardized</h5>
        <p class>
          <strong>All of our courses use the standardized HSK curriculum</strong>. &nbsp;When you complete a course, you will be able to pass the HSK
          test for that level so you can measure your progress and prove your
          ability.&nbsp; Carefully designed lessons following a well established
          program delivers real, measurable results. All courses follow the
          <strong>HSK Standard Course textbook by Jiang Liping.</strong>
        </p>
      </div>
      <div class="col-sm-6">
        <h3>Achieve fluent communication and outstanding HSK results.</h3>
        <p>
          A question commonly posed is, why do you have one of the best-selling
          HSK courses on the web? The answers lie in the instructional
          philosophy behind our courses. This page outlines some of the
          important differences between our courses and other learning products
          commonly found on the web.
        </p>
        <p>
          First of all, our courses aim to form a
          <strong>complete</strong> suit with
          <strong>progressive</strong> and
          <strong>interconnecting units</strong>. Rather than littering the
          collection with disjointed one-shot lessons, our material forms a
          complete whole – a series of step-by-step video-based instructional
          units that take a beginner beyond the highest level, progressing from
          HSK level 1 all the way through HSK level 6 and beyond. Such an
          integrated approach reassures the students that once they sign up with
          us they will be shown a clear path to success, thus saving them
          considerable amount of time and uncertainty.
        </p>
        <p>
          Granted, to be successful in acquiring Chinese as a second language, a
          learners need much more than a set of courses. They must be willing to
          make use of a variety of resources and expose themselves to large
          amounts of the target language through reading and listening.
          <span
            data-offset-key="e61re-0-0"
          >Nevertheless, our courses can form the</span>
          <span data-offset-key="e61re-0-1">
            “
            <strong>backbone</strong>“
          </span>
          <span data-offset-key="e61re-0-2">
            of their learning, providing the structure students can base their
            learning on.
          </span>&nbsp;Learners will find unparalleled success if they take our
          courses in conjunction with the vast array of learning options out
          there.
        </p>
        <p>
          Second, our courses put the spotlight on what many students struggle
          with –
          <strong>grammar</strong>. Without proper knowledge of grammar,
          learners cannot accurately understand what they read or hear. In this
          regard, dictionaries are not particularly helpful because they do not
          explain sentence formation, at least not in a way that is clear to
          students at varying levels. Learning sentence formation is especially
          critical at the beginning stages where learners are utterly oblivious
          of even the most basic sentence patterns. As a result, many learners
          often resort to “guessing” by applying English grammar to Chinese
          sentences and misconstrue their meaning.&nbsp;
          <span>
            Therefore, to learn Chinese effectively, grammar instruction cannot
            be overlooked.
          </span>
        </p>
        <p>
          <span>
            Some resist the idea of explicitly learning grammar in favor of a
            more natural, input-based approach. We agree to this assertion to
            some extent because the nuances of Chinese grammar simply cannot be
            taught with explicit instruction alone. Nevertheless, input is only
            meaningful if they are understood. If learners are never taught
            grammar, how can they possibly understand sentences correctly? It is
            obvious, therefore, that some grammar must be made familiar to the
            students, especially at the beginning stages. Our grammar
            instruction strives to be&nbsp;
          </span>
          <strong class="s570a4-14 kYTLgH">simple and clear with ample examples&nbsp;</strong>
          <span>
            so that the learners can form sentences correctly without being
            unduly concerned with jargons and terms.
          </span>
        </p>
        <p>
          In short,
          <strong>
            curricular completeness and clear, step-by-step grammar
            instruction
          </strong>
          distinguishes us from most learning products out there. We hope these
          courses offer a meaningful contribution to the Chinese learning
          community.
        </p>
      </div>
    </div>

    </div>
  </div>
</template>

<script>
import YouTubeVideo from '@/components/YouTubeVideo'
import Sale from '@/components/Sale'

export default {
  components: {
    YouTubeVideo,
    Sale
  }
}
</script>

<style>

.photo-jon,
.photo-ken {
  position: absolute;
  bottom: 0;
}
.photo-jon {
  height: 70%;
  right: 0;
}
.photo-ken {
  height: 90%;
  left: 0;
}
</style>