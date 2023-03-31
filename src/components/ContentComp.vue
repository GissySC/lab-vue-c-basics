<template>
    <section id="iterations2-3">
        <h1>The result of 2 + 2 is: {{ state.count }}</h1>
        <p>{{ getMyString() }}</p>
        <img v-if="state.count === 4" src="https://media.tenor.com/sgI6lR8JorUAAAAM/lossimpsons-baile.gif">
        <button @click="incrementCount" :class="`btn-${getButtonClass()}`" v-if="showButton" >Try Again</button>
    </section>
    <section id="team">
        <h1> Meet our team!</h1>
        <div id="iteration-4">
            <ul>
                <li v-for="(worker, index) in elements" :key="index">
                    <img class="worker-image" :src="worker.image">
                    <div class="worker-info">
                        <h2>{{ worker.name }} - {{ worker.profession }}</h2>
                        <p>{{ worker.description }}</p>
                    </div>
                </li>
            </ul>
        </div>
    </section>
</template>

<script>
export default {
    name: 'ContentComp',
    data() {
        return {
            msg1: '',
            msg2: '',
            elements: [
                {
                    image: 'https://outwardhound.com/furtropolis/wp-content/uploads/2018/09/corgi-with-glasses-on.jpg',
                    name: 'Aslan',
                    profession: 'Founder & CEO',
                    description: 'Aslan is a visionary entrepreneur with a great passion for his work. As the founder of the company, he has carried out a solid and well-defined strategy, which has led to the growth and success of the company.',
                },
                {
                    image: 'https://pbs.twimg.com/media/C0xCqELWQAAsila?format=jpg&name=small',
                    name: 'Steisy',
                    profession: 'CMO',
                    description: "Steisy is a creative and savvy marketing professional. As the CMO, she leads the company's marketing efforts, working tirelessly to develop innovative and effective campaigns that drive the brand and increase sales."
                },
                {
                    image: 'https://go-pear.org/wp-content/uploads/2021/02/dog-and-computer-scaled.jpg',
                    name: 'Max',
                    profession: 'Programmer',
                    description: " Max is a talented programmer with a passion for technology. With an analytical and logical mind, he works to develop innovative and effective solutions for the company"
                },
                {
                    image: 'https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhKtP1p5r0cmgDbIP6tDmus4g_OnsBEwR2xzQT2VOzvE4S4ns6g7SAvwNknN1HmXntxIVurEymbL86ziDrZb1LDN2SzVVWLnxW8UjxHX5b1nOS7WbLuszN_uYqg427O79F0fRe0ahfjUZPCgIykciX7m_F7rdnZYqmPnOZHZ2B59Nxci1X-o-E9pdh-/s1650/Working_from_home_office_during_pandemic_Pomeranian_in_office_attire_working_on_laptop_Photo_Cookie_The_Pom_on_Unsplash.jpg',
                    name: 'Cora',
                    profession: 'Sales Manager',
                    description: "Cora is very energetic and charismatic, perfect for leading the company's sales team. With her natural ability to communicate with people, Cora is able to build strong relationships with customers."
                }
            ],
            state : {
                count: 1,
                maxCount: 4
            }
        }
    },
    methods: {
        getMyString() {
            return `${this.msg1} ${this.msg2}`;
        },
        incrementCount() {
            if (this.state.count < this.state.maxCount) {
                this.state.count++;
            }
        },
        getButtonClass() {
            if (this.state.count === 2) {
                this.msg1 = "Whoopsie! That's not the answer we were looking for.";
                this.msg2 = "How about one more attempt?";
                return 'firstError';
            }
            if (this.state.count === 3) {
                this.msg1 = "Hmm... close, but no cigar.";
                this.msg2 = "Don't worry, you'll get it next time!";
                return 'secondError';
            }
            if (this.state.count === 4) {
                this.msg1 = "Woohoo!";
                this.msg2 ="Victory dance time!";
                return 'right';
            }
            return 'normal';
        }
    },
    props: {
        showButton: {
            type: Boolean,
            validator(value) {
                return value === true;
            }
        }
    }
}
</script>

<style scoped>

    #iterations2-3 {
        background-color: black;
        text-align: center;
        display: flex;
        flex-direction: column;
        align-items: center;
        color: white;
        padding-top: 20px;
    }

    img {
        width: 8%;
    }

    button {
        margin-bottom: 30px;
        font-size: 17px;
        padding: 5px;
        border-radius: 10px;
    }

    #team {
        background-color: gainsboro;
    }

    #team h1 {
        text-align: center;
        color: black;
        font-size: 30px;
        font-weight: 700;   
        padding: 10px 0; 
    }

    #iteration-4 {
        text-align: center;
        display: flex;
        place-content: center;
        padding-bottom: 30px;    
    }
    .worker-image {
            width: 100%;
            height: 200px;
            object-fit: cover;  
        }

    ul {
        display: flex;
        flex-wrap: wrap;
    }

    li {
        background-color: cadetblue;
        display: flex;
        flex-flow: column wrap;
        padding: 5px;
        margin: 10px;
        text-align: center;
        border-radius: 10px;
        width: 300px;
        color: black;
    }

    li h2 {
        font-weight: 500;
    }

    .worker-info p {
        margin: 10px;
    }

    .btn-firstError {
        background-color: orange;
    }

    .btn-secondError {
        background-color: red;
    }

    .btn-right {
        background-color: greenyellow;
    }
    
</style>