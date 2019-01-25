<template>
  <div class="contact">
    <form name="contact" method="POST" data-netlify="true">
      <FormGroup label="名前">
        <Input label="姓:" name="lastname" />
        <Input label="名:" name="firstname" />
      </FormGroup>
      <FormGroup label="カナ">
        <Input label="セイ:" name="lastname_kana" />
        <Input label="メイ:" name="firstname_kana" />
      </FormGroup>
      <FormGroup label="性別">
        <RadioGroup>
          <Radio name="sex" :value="1" v-model="form.radio1">男性</Radio>
          <Radio name="sex" :value="2" v-model="form.radio1">女性</Radio>
        </RadioGroup>
      </FormGroup>
      <FormGroup label="年齢">
        <Input name="age" />
      </FormGroup>
      <FormGroup label="住所" class="address">
        <FormGroup label="郵便番号">
          <Input label="〒" name="zip_code" />
        </FormGroup>
        <FormGroup label="都道府県">
          <Input label="" name="state" />
        </FormGroup>
        <FormGroup label="市区町村">
          <Input label="" name="city" />
        </FormGroup>
        <FormGroup label="番地・マンション">
          <Input label="" name="street" />
        </FormGroup>
        <FormGroup label="メールアドレス">
          <Input label="" name="email" />
        </FormGroup>
        <FormGroup label="電話番号">
          <Input label="" name="tel" />
        </FormGroup>
      </FormGroup>
      <FormGroup label="最終学歴">
        <Select label="" name="background[]" :options="background">
          <template slot-scope="props">
            <option v-for="(option, key) in props.options"
                    :key="key"
                    :value="option.id"
                    :selected="form.select === option.id"
            >{{ option.value }}
            </option>
          </template>
        </Select>
      </FormGroup>
      <FormGroup label="URL">
        <Input name="site" />
        <span>※Twitter・Facebook・個人サイト・ブログなどがあれば</span>
      </FormGroup>
      <FormGroup label="現在の状態">
        <Select label="" name="req_status[]" :options="status">
          <template slot-scope="props">
            <option v-for="(option, key) in props.options"
                    :key="key"
                    :value="option.id"
                    :selected="form.select === option.id"
            >{{ option.value }}
            </option>
          </template>
        </Select>
      </FormGroup>
      <h2>職歴と業務実績</h2>
      <FormGroup label="会社名">
        <Input name="company_name1" />
      </FormGroup>
      <FormGroup label="職種">
        <Input name="job_title1" />
      </FormGroup>
      <FormGroup label="勤務期間">
        <Select label="年" name="term1_1[]" :options="year" cls="date">
          <template slot-scope="props">
            <option v-for="(option, key) in props.options"
                    :key="key"
                    :value="option.id"
                    :selected="form.select === option.id"
            >{{ option.value }}
            </option>
          </template>
        </Select>
        <Select label="月〜" name="term1_2[]" :options="month" cls="date">
          <template slot-scope="props">
            <option v-for="(option, key) in props.options"
                    :key="key"
                    :value="option.id"
                    :selected="form.select === option.id"
            >{{ option.value }}
            </option>
          </template>
        </Select>
        <Select label="年" name="term1_3[]" :options="year" cls="date">
          <template slot-scope="props">
            <option v-for="(option, key) in props.options"
                    :key="key"
                    :value="option.id"
                    :selected="form.select === option.id"
            >{{ option.value }}
            </option>
          </template>
        </Select>
        <Select label="月" name="term1_4[]" :options="month" cls="date">
          <template slot-scope="props">
            <option v-for="(option, key) in props.options"
                    :key="key"
                    :value="option.id"
                    :selected="form.select === option.id"
            >{{ option.value }}
            </option>
          </template>
        </Select>
      </FormGroup>
      <FormGroup label="雇用形態">
        <Select label="" name="req_status[]" :options="titles">
          <template slot-scope="props">
            <option v-for="(option, key) in props.options"
                    :key="key"
                    :value="option.id"
                    :selected="form.select === option.id"
            >{{ option.value }}
            </option>
          </template>
        </Select>
      </FormGroup>
      <FormGroup label="これまでに手がけた作品やプロジェクト">
        <label><textarea name="appeal"></textarea></label>
      </FormGroup>
      <h2>志望動機・自己PR</h2>
      <FormGroup label="希望する職種">
        株式会社パノラマ / プロデューサー / ディレクター
      </FormGroup>
      <FormGroup label="志望動機">
        <label><textarea name="message"></textarea></label>
      </FormGroup>
      <FormGroup label="雇用形態">
        <Select label="" name="req_status[]" :options="titles">
          <template slot-scope="props">
            <option v-for="(option, key) in props.options"
                    :key="key"
                    :value="option.id"
                    :selected="form.select === option.id"
            >{{ option.value }}
            </option>
          </template>
        </Select>
      </FormGroup>
      <FormGroup label="自己 PR / 自由記入欄">
        <label><textarea name="pr"></textarea></label>
      </FormGroup>
      <div>
        <h3>個人情報の取り扱いについて</h3>
        <p>テキストテキスト</p>
        <button type="submit">送信</button>
      </div>
    </form>
  </div>
</template>

<script>
  import Input from '~/components/atoms/Input'
  import Radio from '~/components/atoms/Radio'
  import Select from '~/components/atoms/Select'
  import FormGroup from '~/components/molecules/FormGroup'
  import RadioGroup from '~/components/molecules/RadioGroup'
  export default {
    components : {
      Input, Radio, RadioGroup, Select, FormGroup
    },
    data: () => ({
      form: {
        radio1: 1,
        select: 0
      },
      status: [
        { id: 0, value: '選択してください'},
        { id: 1, value: '在職中'},
        { id: 2, value: 'フリーランス'},
        { id: 3, value: 'フリーター（アルバイト）'},
        { id: 4, value: '無職'}
      ],
      titles: [
        { id: 0, value: '選択してください'},
        { id: 1, value: '正社員'},
        { id: 2, value: '契約社員'},
        { id: 3, value: '業務委託'},
        { id: 4, value: 'アルバイト'},
        { id: 5, value: 'インターン'}
      ],
      background: [
        { id: 0, value: '選択してください'},
        { id: 1, value: '卒業'},
        { id: 2, value: '卒業見込み'},
        { id: 3, value: '在学中'},
        { id: 4, value: '中退'}
      ],
      year: [
        { id: 0, value: '----'},
        { id: 1980, value: '1980'},
        { id: 1981, value: '1981'},
        { id: 1982, value: '1982'},
        { id: 1983, value: '1983'},
        { id: 1984, value: '1984'},
        { id: 1985, value: '1985'},
        { id: 1986, value: '1986'},
        { id: 1987, value: '1987'},
        { id: 1988, value: '1988'},
        { id: 1989, value: '1989'},
        { id: 1990, value: '1990'},
        { id: 1991, value: '1991'},
        { id: 1992, value: '1992'},
        { id: 1993, value: '1993'},
        { id: 1994, value: '1994'},
        { id: 1995, value: '1995'},
        { id: 1996, value: '1996'},
        { id: 1997, value: '1997'},
        { id: 1998, value: '1998'},
        { id: 1999, value: '1999'},
        { id: 2000, value: '2000'},
        { id: 2001, value: '2001'},
        { id: 2002, value: '2002'},
        { id: 2003, value: '2003'},
        { id: 2004, value: '2004'},
        { id: 2005, value: '2005'},
        { id: 2006, value: '2006'},
        { id: 2007, value: '2007'},
        { id: 2008, value: '2008'},
        { id: 2009, value: '2009'},
        { id: 2010, value: '2010'},
        { id: 2011, value: '2011'},
        { id: 2012, value: '2012'},
        { id: 2013, value: '2013'},
        { id: 2014, value: '2014'},
        { id: 2015, value: '2015'},
        { id: 2016, value: '2016'},
        { id: 2017, value: '2017'},
        { id: 2018, value: '2018'},
        { id: 2019, value: '2019'}
      ],
      month: [
        { id: 0, value: '----'},
        { id: 1, value: '1'},
        { id: 2, value: '2'},
        { id: 3, value: '3'},
        { id: 4, value: '4'},
        { id: 5, value: '5'},
        { id: 6, value: '6'},
        { id: 7, value: '7'},
        { id: 8, value: '8'},
        { id: 9, value: '9'},
        { id: 10, value: '10'},
        { id: 11, value: '11'},
        { id: 12, value: '12'}
      ]
    })
  }
</script>

<style lang="scss" scoped>
  .contact {
    padding: 50px 0;
    background-color: #f6f5f6;
    form {
      width: 864px;
      margin: 0 auto;
    }
    h2 {
      font-size: 1.2rem;
      letter-spacing: .1em;
      text-align: center;
      padding: 20px 0;
    }
    /deep/ dl dl {
      align-items: center;
    }
    /deep/ dl div:last-child dl {
      border-bottom: none;
      padding-bottom: 0;
      margin-bottom: 0;
    }
  }
  textarea {
    border-radius: 4px;
    border: 1px solid #cecece;
    padding: 5px;
    width: 100%;
    display: block;
  }
</style>
