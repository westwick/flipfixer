<template>
  <div
    class="h-screen flex justify-end items-center p-5 bg-[#0a0a0a] bg-cover relative"
    style="background-image: url('/assets/images/homebg.png')"
  >
    <div class="w-2/5 mr-[5%] relative">
      <h1 class="text-4xl font-bold mb-16 text-white glowy-text">
        ORIGIN OF THE ROAR
      </h1>

      <div class="flex flex-col gap-12">
        <div
          v-for="(text, index) in texts"
          :key="index"
          class="timeline-item group relative"
          :style="{
            marginLeft: `${linePositions[index].start}px`,
            paddingTop: `${index * 10}px`,
          }"
        >
          <svg
            class="timeline-svg absolute"
            :width="linePositions[index].width"
            height="24"
            :viewBox="`0 0 ${linePositions[index].width} 24`"
          >
            <line
              x1="0"
              y1="12"
              :x2="linePositions[index].width"
              y2="12"
              stroke="white"
              stroke-width="2"
              class="timeline-line"
            />
            <circle
              :cx="linePositions[index].width"
              cy="12"
              r="12"
              fill="transparent"
              class="timeline-hover-area"
            />
            <circle
              :cx="linePositions[index].width"
              cy="12"
              r="4"
              fill="white"
              class="timeline-circle"
            />
          </svg>
          <p
            class="timeline-text text-gray-300 text-sm leading-relaxed opacity-20 group-hover:opacity-80 transition-opacity duration-300"
            :style="{ marginLeft: `${linePositions[index].width + 20}px` }"
          >
            {{ text }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AboutPage",
  data() {
    return {
      texts: [
        "In the heart of digital innovation, our journey began with a vision to transform the ordinary into the extraordinary. The roar represents our unwavering commitment to excellence and the fierce determination that drives every project we undertake.",
        "Our philosophy is rooted in the belief that great design should not just be seen, but felt. Like a lion's roar echoing through the digital landscape, our work aims to leave a lasting impression that resonates with audiences across all platforms.",
        "With years of experience in creative innovation, we've developed a unique approach that combines cutting-edge technology with timeless design principles. Each project is crafted with precision, passion, and an unwavering attention to detail.",
        "We believe in pushing boundaries and challenging conventions. Our team of dedicated professionals works tirelessly to create solutions that not only meet but exceed expectations, setting new standards in digital excellence.",
      ],
      linePositions: [
        { start: -80, width: 160 },
        { start: -160, width: 240 },
        { start: -120, width: 200 },
        { start: -140, width: 220 },
      ],
    };
  },
};
</script>

<style>
.timeline-item {
  display: flex;
  align-items: center;
  position: relative;
  min-height: 24px;
}

.timeline-svg {
  flex-shrink: 0;
  overflow: visible;
  left: 0;
  z-index: 1;
}

.timeline-line {
  transform-origin: left;
  animation: growLine 0.6s ease-out forwards;
  transform: scaleX(0);
}

.timeline-circle {
  animation: fadeIn 0.3s ease-out 0.6s forwards;
  opacity: 0;
  transition: transform 0.2s ease;
}

.timeline-hover-area {
  cursor: pointer;
}

.timeline-text {
  position: relative;
  max-width: 500px;
  transition: all 0.3s ease;
  z-index: 2;
}

@keyframes growLine {
  from {
    transform: scaleX(0);
  }
  to {
    transform: scaleX(1);
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

/* Stagger the animations for each timeline item */
.timeline-item:nth-child(1) .timeline-line {
  animation-delay: 0s;
}
.timeline-item:nth-child(1) .timeline-circle {
  animation-delay: 0.6s;
}

.timeline-item:nth-child(2) .timeline-line {
  animation-delay: 0.2s;
}
.timeline-item:nth-child(2) .timeline-circle {
  animation-delay: 0.8s;
}

.timeline-item:nth-child(3) .timeline-line {
  animation-delay: 0.4s;
}
.timeline-item:nth-child(3) .timeline-circle {
  animation-delay: 1s;
}

.timeline-item:nth-child(4) .timeline-line {
  animation-delay: 0.6s;
}
.timeline-item:nth-child(4) .timeline-circle {
  animation-delay: 1.2s;
}

/* Update the hover effect */
.timeline-item:hover .timeline-circle {
  r: 5;
}

.glowy-text {
  position: relative;
  text-shadow: 0 0 10px rgba(255, 255, 255, 0.3),
    0 0 20px rgba(255, 255, 255, 0.2), 0 0 30px rgba(255, 255, 255, 0.1);
  animation: textDistort 4s ease-in-out infinite;
}

.glowy-text::before {
  content: "ORIGIN OF THE ROAR";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  filter: blur(8px);
  opacity: 0.7;
  animation: glowPulse 4s ease-in-out infinite;
}

@keyframes textDistort {
  0%,
  100% {
    transform: skew(0deg, 0deg);
    letter-spacing: normal;
  }
  25% {
    transform: skew(-1deg, 0.5deg);
    letter-spacing: 1px;
  }
  75% {
    transform: skew(1deg, -0.5deg);
    letter-spacing: -0.5px;
  }
}

@keyframes glowPulse {
  0%,
  100% {
    filter: blur(8px);
    opacity: 0.7;
  }
  50% {
    filter: blur(12px);
    opacity: 0.9;
  }
}
</style>
