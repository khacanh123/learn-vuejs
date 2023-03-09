<template>
    <div>
        <div v-for="item in currentQuestion">
            <div>Câu {{ 1 }}:
                <MathJax v-bind:math="item.text" />
            </div>
            <MultiChoiceOnRight v-bind:answer="item.listSelectOptions" v-on:check="checkFunc" />
        </div>
        <div class="flex justify-between">
            <button @click="index - 1" v-if="checkButtonDisplay">Câu trước đó</button>
            <button @click="index++">Câu tiếp theo</button>
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted, watch } from 'vue'
import MathJax from '../components/MathJax.vue';
import MultiChoiceOnRight from '../components/MultiChoiceOnRight.vue';
const index = ref(0)
const checkButtonDisplay = ref(true)
const currentQuestion = ref([])
const listQuestion = ref([
    {
        "_id": "62957c8528960f76028598bf",
        "_companyShareIdKey": 1,
        "name": null,
        "text": "Rút gọn biểu thức. \\[\\sin \\left( a-{{17}^{0}} \\right). \\cos \\left( a+{{13}^{0}} \\right)\\sin \\left( a+{{13}^{0}} \\right). \\cos \\left( a-{{17}^{0}} \\right)\\], ta được.",
        "text_latex": null,
        "isMathFormula": false,
        "quiz_type": 1,
        "level": 0,
        "type": 1,
        "awareness_level": 1,
        "answer_type": 0,
        "solution": "Ta có. \\[\\sin \\left( a-{{17}^{0}} \\right). \\cos \\left( a+{{13}^{0}} \\right)\\sin \\left( a+{{13}^{0}} \\right). \\cos \\left( a-{{17}^{0}} \\right)=\\sin \\left[ \\left( a-{{17}^{0}} \\right)-\\left( a+{{13}^{0}} \\right) \\right]\\]<br /> $$ =\\sin \\left( -{{30}^{0}} \\right)=-\\frac{1}{2}. $$",
        "listClass": [
            10
        ],
        "listSubject": [
            1
        ],
        "listKnowledgeUnit": [],
        "listTag": [],
        "count": 0,
        "count_turns_correct": 0,
        "listShortAnswer": null,
        "listPairOptions": {
            "keys": null,
            "values": null
        },
        "listSortOptions": null,
        "idQuestion": 39649,
        "image": "",
        "audio": null,
        "video": null,
        "solution_image": null,
        "solution_audio": null,
        "solution_video": null,
        "listSelectOptions": [
            {
                "answer_content": " \\[\\sin 2a. \\] ",
                "answer_content_latex": null,
                "answer_url_image": "",
                "answer_url_mp3": "",
                "is_true": false,
                "answer_id": 122955
            },
            {
                "answer_content": " \\[\\cos 2a. \\] ",
                "answer_content_latex": null,
                "answer_url_image": "",
                "answer_url_mp3": "",
                "is_true": false,
                "answer_id": 122954
            },
            {
                "answer_content": " \\[-\\frac{1}{2}. \\] ",
                "answer_content_latex": null,
                "answer_url_image": "",
                "answer_url_mp3": "",
                "is_true": true,
                "answer_id": 122957
            },
            {
                "answer_content": " \\[\\frac{1}{2}. \\]<br /> ",
                "answer_content_latex": null,
                "answer_url_image": "",
                "answer_url_mp3": "",
                "is_true": false,
                "answer_id": 122956
            }
        ],
        "listQuestionChildren": [],
        "weight": 2
    },
    {
        "_id": "6344eb8b1d064197e748937c",
        "_companyShareIdKey": 1,
        "name": "Câu 3 app",
        "text": "<p>Trong các số sau, số nào chia hết cho <i><strong>2&nbsp;</strong></i></p><p>&nbsp;</p>",
        "text_latex": "<p>Trong các số sau, số nào chia hết cho <i><strong>2&nbsp;</strong></i></p><p>&nbsp;</p>",
        "isMathFormula": false,
        "quiz_type": 2,
        "level": 0,
        "type": 1,
        "awareness_level": 0,
        "answer_type": 0,
        "solution": "",
        "listClass": [
            4
        ],
        "listSubject": [
            1
        ],
        "listKnowledgeUnit": [],
        "listTag": [],
        "count": 142,
        "count_turns_correct": 28,
        "listShortAnswer": null,
        "listPairOptions": {
            "keys": null,
            "values": null
        },
        "listSortOptions": null,
        "speakElsa": null,
        "idQuestion": 189801,
        "image": "",
        "audio": "",
        "video": "",
        "solution_image": "",
        "solution_audio": null,
        "solution_video": null,
        "listSelectOptions": [
            {
                "answer_content": "<p>1998</p>",
                "answer_content_latex": null,
                "answer_url_image": "",
                "answer_url_mp3": null,
                "is_true": true,
                "answer_id": 671239
            },
            {
                "answer_content": "<p>1235</p>",
                "answer_content_latex": null,
                "answer_url_image": "",
                "answer_url_mp3": null,
                "is_true": false,
                "answer_id": 671240
            },
            {
                "answer_content": "<p>2469</p>",
                "answer_content_latex": null,
                "answer_url_image": "",
                "answer_url_mp3": null,
                "is_true": false,
                "answer_id": 671241
            },
            {
                "answer_content": "<p>2222</p>",
                "answer_content_latex": null,
                "answer_url_image": "",
                "answer_url_mp3": null,
                "is_true": true,
                "answer_id": 671242
            }
        ],
        "listQuestionChildren": [],
        "weight": 3
    },
    {
        "_id": "63eeecb01b98b38b3d65e54c",
        "_companyShareIdKey": 1,
        "name": "M07_R1_007",
        "text": "Trong không gian <math><mi>O</mi><mi>x</mi><mi>y</mi><mi>z</mi></math>, cho điểm <math><mi>M</mi><mfenced close=\")\" open=\"(\" separators=\"\"><mn>2</mn><mo>;</mo><mo>−</mo><mn>1</mn><mo>;</mo><mo>−</mo><mn>3</mn></mfenced></math>. Tìm tọa độ điểm <math><mi>M</mi><mo>'</mo></math> đối xứng với điểm <math><mi>M</mi></math> qua trục <math><mi>O</mi><mi>y</mi></math>.</p><p>",
        "text_latex": "Trong không gian $Oxyz$, cho điểm $M\\left(2,;,-,1,;,-,3\\right)$. Tìm tọa độ điểm $M'$ đối xứng với điểm $M$ qua trục $Oy$.</p><p>",
        "isMathFormula": true,
        "quiz_type": 1,
        "level": 2,
        "type": 1,
        "awareness_level": 2,
        "answer_type": 0,
        "solution": null,
        "listClass": [
            7
        ],
        "listSubject": [
            1
        ],
        "listKnowledgeUnit": [],
        "listTag": [
            209,
            209,
            209,
            209,
            209,
            209,
            209
        ],
        "count": 0,
        "count_turns_correct": 0,
        "listShortAnswer": null,
        "listPairOptions": {
            "keys": null,
            "values": null
        },
        "listSortOptions": null,
        "speakElsa": null,
        "listCheckOptions": [],
        "idQuestion": 190412,
        "image": null,
        "audio": null,
        "video": null,
        "solution_image": null,
        "solution_audio": null,
        "solution_video": null,
        "listSelectOptions": [
            {
                "answer_content": "<math><mi>M</mi><mo>'</mo><mfenced close=\")\" open=\"(\" separators=\"\"><mo>−</mo><mn>2</mn><mo>;</mo><mo>−</mo><mn>1</mn><mo>;</mo><mo>−</mo><mn>3</mn></mfenced></math>.",
                "answer_content_latex": "$M'\\left(-,2,;,-,1,;,-,3\\right)$.",
                "answer_url_image": null,
                "answer_url_mp3": null,
                "is_true": false,
                "idCheck": null,
                "answer_id": 673985
            },
            {
                "answer_content": "<math><mi>M</mi><mo>'</mo><mfenced close=\")\" open=\"(\" separators=\"\"><mo>−</mo><mn>2</mn><mo>;</mo><mo>−</mo><mn>1</mn><mo>;</mo><mn>3</mn></mfenced></math>.</p><p>",
                "answer_content_latex": "$M'\\left(-,2,;,-,1,;,3\\right)$.</p><p>",
                "answer_url_image": null,
                "answer_url_mp3": null,
                "is_true": true,
                "idCheck": null,
                "answer_id": 673986
            },
            {
                "answer_content": "<math><mi>M</mi><mo>'</mo><mfenced close=\")\" open=\"(\" separators=\"\"><mn>2</mn><mo>;</mo><mo>−</mo><mn>1</mn><mo>;</mo><mn>3</mn></mfenced></math>.",
                "answer_content_latex": "$M'\\left(2,;,-,1,;,3\\right)$.",
                "answer_url_image": null,
                "answer_url_mp3": null,
                "is_true": false,
                "idCheck": null,
                "answer_id": 673987
            },
            {
                "answer_content": "<math><mi>M</mi><mo>'</mo><mfenced close=\")\" open=\"(\" separators=\"\"><mn>2</mn><mo>;</mo><mn>1</mn><mo>;</mo><mo>−</mo><mn>3</mn></mfenced></math>.</p><p>",
                "answer_content_latex": "$M'\\left(2,;,1,;,-,3\\right)$.</p><p>",
                "answer_url_image": null,
                "answer_url_mp3": null,
                "is_true": false,
                "idCheck": null,
                "answer_id": 673988
            }
        ],
        "listQuestionChildren": [],
        "weight": 1
    },
    {
        "_id": "63eeecaf1b98b38b3d65e4c9",
        "_companyShareIdKey": 1,
        "name": "M07_R1_002",
        "text": "Một vật chuyển động với phương trình vận tốc là <math><mi>v</mi><mfenced close=\")\" open=\"(\" separators=\"\"><mi>t</mi></mfenced><mo>=</mo><mn>5</mn><mo>+</mo><mn>2</mn><mi>t</mi><mspace width=\"0.08em\"/><mfenced close=\")\" open=\"(\" separators=\"\"><mi>m</mi><mo>/</mo><mi>s</mi></mfenced></math>. Hỏi quãng đường vật di chuyển được trong <math><mn>5</mn></math> giây đầu tiên?</p><p>",
        "text_latex": "Một vật chuyển động với phương trình vận tốc là $v\\left(t\\right)=5+2t\\left(m,/,s\\right)$. Hỏi quãng đường vật di chuyển được trong $5$ giây đầu tiên?</p><p>",
        "isMathFormula": true,
        "quiz_type": 1,
        "level": 0,
        "type": 1,
        "awareness_level": 1,
        "answer_type": 0,
        "solution": "</p><p>Quãng đường vật di chuyển được là: <math><mi>S</mi><mo>=</mo><mstyle displaystyle=\"true\"><munderover><mo>∫</mo><mn>0</mn><mn>5</mn></munderover><mrow><mfenced close=\")\" open=\"(\" separators=\"\"><mn>5</mn><mo>+</mo><mn>2</mn><mi>t</mi></mfenced><mtext>dt</mtext></mrow></mstyle><mspace width=\"0.08em\"/><mo>=</mo><mspace width=\"0.08em\"/><mfenced close=\")\" open=\"(\" separators=\"\"><mn>5</mn><mi>t</mi><mo>+</mo><msup><mi>t</mi><mn>2</mn></msup></mfenced><mfenced close=\"\" open=\"|\" separators=\"\"><mtable columnalign=\"left\"><mtr><mtd><mn>5</mn></mtd></mtr><mtr><mtd><mn>0</mn></mtd></mtr></mtable></mfenced><mo>=</mo><mn>5</mn><mo>.</mo><mn>5</mn><mo>+</mo><msup><mn>5</mn><mn>2</mn></msup><mo>=</mo><mn>50</mn><mspace width=\"0.08em\"/><mfenced close=\")\" open=\"(\" separators=\"\"><mi>m</mi></mfenced></math>.</p><p>",
        "listClass": [
            7
        ],
        "listSubject": [
            1
        ],
        "listKnowledgeUnit": [],
        "listTag": [
            209,
            209,
            209,
            209,
            209,
            209,
            209
        ],
        "count": 0,
        "count_turns_correct": 0,
        "listShortAnswer": null,
        "listPairOptions": {
            "keys": null,
            "values": null
        },
        "listSortOptions": null,
        "speakElsa": null,
        "listCheckOptions": [],
        "idQuestion": 190407,
        "image": null,
        "audio": null,
        "video": null,
        "solution_image": null,
        "solution_audio": null,
        "solution_video": null,
        "listSelectOptions": [
            {
                "answer_content": "<math><mn>100</mn><mspace width=\"0.08em\"/><mfenced close=\")\" open=\"(\" separators=\"\"><mi>m</mi></mfenced></math>.",
                "answer_content_latex": "$100\\left(m\\right)$.",
                "answer_url_image": null,
                "answer_url_mp3": null,
                "is_true": false,
                "idCheck": null,
                "answer_id": 673965
            },
            {
                "answer_content": "50 (<em>m</em>).",
                "answer_content_latex": "50 (<em>m</em>).",
                "answer_url_image": null,
                "answer_url_mp3": null,
                "is_true": true,
                "idCheck": null,
                "answer_id": 673966
            },
            {
                "answer_content": "<math><mn>40</mn><mspace width=\"0.08em\"/><mspace width=\"0.08em\"/><mfenced close=\")\" open=\"(\" separators=\"\"><mi>m</mi></mfenced></math>.",
                "answer_content_latex": "$40\\left(m\\right)$.",
                "answer_url_image": null,
                "answer_url_mp3": null,
                "is_true": false,
                "idCheck": null,
                "answer_id": 673967
            },
            {
                "answer_content": "<math><mn>10</mn><mspace width=\"0.08em\"/><mspace width=\"0.08em\"/><mfenced close=\")\" open=\"(\" separators=\"\"><mi>m</mi></mfenced></math>.</p><p>",
                "answer_content_latex": "$10\\left(m\\right)$.</p><p>",
                "answer_url_image": null,
                "answer_url_mp3": null,
                "is_true": false,
                "idCheck": null,
                "answer_id": 673968
            }
        ],
        "listQuestionChildren": [],
        "weight": 1
    }
])

onMounted(() => {
    currentQuestion.value = listQuestion.value.slice(index, index + 1)
    console.log('====================================');
    console.log(listQuestion.value);
    console.log('====================================');
    let a = 1;
    const b = 1
})


const checkFunc = (aaa) => {

}
</script>
<style>
button {
    border: 1px solid;
    width: 100px;
}
</style>