<template>
  <v-container>
    <v-layout text-center wrap>
      <v-flex xs12>
        <v-btn @click="clickShowAnswer">show Answer</v-btn>
        <v-btn @click="NewQuestion">new Question</v-btn>
      </v-flex>
      <v-flex xs12 display-3>{{ randnum }}</v-flex>
      <v-flex xs12 display-2 v-show="showFarsi">{{ randnumFarsi }}</v-flex>
    </v-layout>
  </v-container>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";

@Component({
})
export default class FarsiNumber extends Vue {
  private randnum: number;
  private showFarsi: boolean;
  private randnumFarsi: string;

  constructor() {
    super();
    this.randnum = 0;
    this.showFarsi = false ;
    this.randnumFarsi = "ANSWER!";
  }

  private mounted(): void {
    this.NewQuestion();
  }

  private clickShowAnswer(): boolean {
    this.showFarsi = true;
    return true;
  }

  private NewQuestion(): boolean {
    this.showFarsi = false ;
    this.randnum = Math.floor(Math.pow(10, Math.random() * 8));
    this.randnumFarsi = this.farsiString(this.randnum, 0);
    return true;
  }

  private farsiString(n: number, prevK: number /* 3桁ごとに1増える */): string {
    if (prevK === 0 && n === 0) {
      return "صفر"; // "sefr";
    }
    const knum = Math.floor(n / 1000);
    const kstr = this.handredString(n - knum * 1000) + this.mstr(prevK);
    const prevstr = knum > 0 ? this.farsiString(knum, prevK + 1) : "";
    return prevstr + (prevstr && kstr ? " و " : "") + kstr;
  }

  private handredString(n: number): string {
    const hnum = Math.floor(n / 100);
    const bnum = n - hnum * 100;
    const hstr = this.hstr(hnum);
    const bstr = this.bstr(bnum);
    return hstr + (hstr && bstr ? " و " : "") + bstr;
  }

  private bstr(bnum: number): string {
    if (bnum < 20) {
      return this.cstr(bnum);
    } else {
      const dnum = Math.floor(bnum / 10);
      const cnum = bnum - dnum * 10;
      const dstr = this.dstr(dnum);
      const cstr = this.cstr(cnum);
      return dstr + (dstr && cstr ? " و " : "") + cstr;
    }
  }

  private mstr(k: number) {
    switch (k) {
      case 0:
        return "";
      case 1:
        return " هزار "; // " hazaar";
      case 2:
        return " میایون "; // " miiliyuun";
    }
    return "";
  }

  private hstr(hnum: number): string {
    switch (hnum) {
      case 0:
        return "";
      case 1:
        return "صد"; // "sad ";
      case 2:
        return "دویست"; // "deviist ";
      case 3:
        return "سیصد"; // "siisad ";
      case 4:
        return "چهارصد"; // "chahaarsad ";
      case 5:
        return "پانصد"; // "paansad ";
      case 6:
        return "ششصد"; // "sheshsad ";
      case 7:
        return "هفتصد"; // "haftdsad ";
      case 8:
        return "هشتصد"; // "hashtsad ";
      case 9:
        return "نهصد"; // "nohsad ";
    }
    return "";
  }

  private dstr(dnum: number): string {
    switch (dnum) {
      case 0:
        return "";
      case 1:
        return "";
      case 2:
        return "بیست"; // "biist";
      case 3:
        return "سی"; // "sii";
      case 4:
        return "چهل"; // "chehel";
      case 5:
        return "پنجاه"; // "panjah";
      case 6:
        return "شصت"; // "shast";
      case 7:
        return "هفتاد"; // "haftaad";
      case 8:
        return "هشتاد"; // "hashtaad";
      case 9:
        return "نود"; // "navad";
    }
    return "";
  }

  private cstr(cnum: number): string {
    switch (cnum) {
      case 0:
        return "";
      case 1:
        return "یک"; // "yek";
      case 2:
        return "دو"; // "do";
      case 3:
        return "سه"; // "se";
      case 4:
        return "چهار"; // "chahar";
      case 5:
        return "پنج"; // "panj";
      case 6:
        return "شش"; // "shish";
      case 7:
        return "هفت"; // "haft";
      case 8:
        return "هشت"; // "hasht";
      case 9:
        return "نه"; // "nou";
      case 10:
        return "ده"; // "dah";
      case 11:
        return "یازده"; // "yazdah";
      case 12:
        return "دوازده"; // "davouzdah";
      case 13:
        return "شیزده"; // "sizdah";
      case 14:
        return "چهارده"; // "chardar";
      case 15:
        return "پانزده"; // "paanzdah";
      case 16:
        return "شانزده"; // "shaanzdah";
      case 17:
        return "هفده"; // "hevdah";
      case 18:
        return "هجده"; // "hejdar";
      case 19:
        return "نوزده"; // "nuuzdar";
    }
    return "";
  }
}
</script>

<style>
</style>
