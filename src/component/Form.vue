<template>
  <div>
    <CRow>
      <CCol sm="6">
        <CCard>
          <CCardHeader>
            <strong>Profile </strong>
            <div class="card-header-actions">
              <a 
                href="https://coreui.io/vue/docs/components/form-components" 
                class="card-header-action" 
                rel="noreferrer noopener" 
                target="_blank"
              >
                <small class="text-muted"></small>
              </a>
            </div>
          </CCardHeader>
          <CCardBody>
            <CRow>
              <CCol sm="6">
                <CInput v-model="username"
                  label="Name"
                  placeholder="Enter your name"
                />
              </CCol>
            </CRow>
            <CRow>
              <CCol sm="6">
                <CInput v-model="myname"
                  label="Surname"
                  placeholder="Enter your surename"
                />
              </CCol>
            </CRow>
         <CSelect v-model="gen"
                label="Gender" 
                horizontal
                :options="['Male','Female']"
                placeholder="Please select"
              />
            <CRow>
                 <CCol sm="6">
              <CInput v-model="bornday"
                label="Birthday"
                type="date"
                horizontal
              />
                 </CCol>
            </CRow>
            <CRow >
              <CCol sm="6">
                <CInput v-model="num"
                  label="Phone Number"
                  placeholder="000-000-0000"
                />
              </CCol>
            </CRow>

            <CSelect v-model="cou"
                label="Country" 
                horizontal
                :options="options"
                placeholder="Please select"
              />
              <CCol sm="8">
                <CInput v-model="ades"
                  label="Address"
                  placeholder="Enter your address"
                />
              </CCol>
              <CCol sm="8">
                <CInput v-model="unis"
                  label="University"
                  placeholder="Enter your university"
                />
              </CCol>
              <CCol sm="8">
                <CInput v-model="shol"
                  label="Faculty/School"
                  placeholder="Enter your faculty/school"
                />
              </CCol>
              <CCol sm="8">
                <CInput v-model="maj"
                  label="Major"
                  placeholder="Enter your major"
                />
              </CCol>
              <CCardFooter>
            <CButton type="update" size="sm" color="primary" @click="this.onregister"><CIcon name="cil-check-circle"/> Update</CButton>
            <CButton type="cancel" size="sm" color="danger"><CIcon name="cil-ban"/> Cancel</CButton>
          </CCardFooter>
          </CCardBody>
        </CCard>
      </CCol>
    </CRow>
      </div>
</template>

<script>
export default {
  name: 'Forms',
  data () {
    return {
      selected: [], // Must be an array reference!
      show: true,
      horizontal: { label:'col-3', input:'col-9' },
      options: ['Option 1', 'Option 2', 'Option 3'],
      selectOptions: [
        'Option 1', 'Option 2', 'Option 3',
        { 
          value: ['some value', 'another value'], 
          label: 'Selected option'
        }
      ],
      selectedOption: ['some value', 'another value'],

      formCollapsed: true,
      checkboxNames: ['Checkboxes', 'Inline Checkboxes',
                      'Checkboxes - custom', 'Inline Checkboxes - custom'],
      radioNames: ['Radios', 'Inline Radios',
                    'Radios - custom', 'Inline Radios - custom']
    }
  }, info () {
    return {
      username:'',
      myname:'',
      gen:'',
      bornday:'',
      num:'',
      cou:'',
      ades:'',
      unis:'',
      shol:'',
      maj:'',
    }
  },
  methods: {
    validator (val) {
      return val ? val.length >= 4 : false
    } , onregister () {
      var info={};
      info.name=this.username;
      info.lastname=this.myname;
      info.mygen=this.gen;
      info.birthday=this.bornday;
      info.number=this.num;
      info.country=this.cou;
      info.address=this.ades;
      info.university=this.unis;
      info.school=this.shol;
      info.major=this.maj;
      console.log(info);
    }
  }
}
</script>
