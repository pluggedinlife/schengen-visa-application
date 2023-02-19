<template>
  <div class="flex h-full flex-1 flex-col space-y-8 p-8 bg-gray-400">
    <div class="text-2xl">Application for Schengen Visa</div>
    <!-- flag image -->
    <div class="flex">
      <div class="flex-1">
        <img
          class="h-24"
          src="data:image/png;base64,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"
          alt="eu-flag"
        />
      </div>
      <div class="h-28 border border-gray-700 p-8 flex items-center">
        Image loading seciton
      </div>
    </div>

    <!-- Has to be hidden on print -->
    <div class="flex flex-col text-xs space-y-2 border-l border-gray-600 pl-2">
      <span>&#9888; Important</span>
      <span>
        The fields marked with * shall not be filled in by family members of EU,
        EEA or CH citizens (spouse, child or dependent ascendant) while
        exercising their right to free movement. Family members of EU, EEA or CH
        citizens shall present documents to prove this relationship and fill in
        fields no 34 and 35. (x) Fields 1-3 shall be filled in in accordance
        with the data in the travel document.
      </span>
    </div>

    <!-- 1,2,3 -->
    <div class="flex flex-col bg-gray-100">
      <span>1. Surname (family name) (x)</span>
      <input class="w-full" type="text" v-model="applicationData.surname" />
    </div>
    <div class="flex flex-col bg-gray-100">
      <span>2. Surname at birth (Former family name(s)) (x)</span>
      <input
        class="w-full"
        type="text"
        v-model="applicationData.surnameAtBirth"
      />
    </div>
    <div class="flex flex-col bg-gray-100">
      <span>3. First name(s) (Given name(s)) (x)</span>
      <input class="w-full" type="text" v-model="applicationData.firstName" />
    </div>

    <!-- 4,5,6,7 -->
    <div class="flex w-full">
      <div class="flex flex-col bg-gray-100 w-full">
        <span>4. Date of birth (day-month-year)</span>
        <input
          class="w-full"
          type="date"
          v-model="applicationData.dateOfBirth"
        />
      </div>
      <div class="flex flex-col w-full">
        <div class="flex flex-col bg-gray-100">
          <span>5. Place of birth</span>
          <input
            class="w-full"
            type="text"
            v-model="applicationData.placeOfBirth"
          />
        </div>
        <div class="flex flex-col bg-gray-100">
          <span>6. Country of birth</span>
          <input
            class="w-full"
            type="text"
            v-model="applicationData.countryOfBirth"
          />
        </div>
      </div>
      <div class="flex flex-col w-full">
        <div class="flex flex-col bg-gray-100">
          <span>7. Current nationality</span>
          <input
            class="w-full"
            type="text"
            v-model="applicationData.currentNationality"
          />
        </div>
        <div class="flex flex-col bg-gray-100">
          <span>Nationality at birth (if different)</span>
          <input
            class="w-full"
            type="text"
            v-model="applicationData.nationalityAtBirth"
          />
        </div>
      </div>
    </div>

    <!-- 8,9 -->
    <div class="flex w-full">
      <div class="flex flex-col w-full bg-gray-100">
        <span>8. Sex</span>
        <div class="flex">
          <div>
            <input
              class="w-full"
              type="checkbox"
              name="male"
              v-model="applicationData.sex.male"
            />
            <label for="male">Male</label>
          </div>
          <div>
            <input
              type="checkbox"
              name="female"
              v-model="applicationData.sex.female"
            />
            <label for="female">Female</label>
          </div>
        </div>
      </div>
      <div class="flex flex-col w-full bg-gray-100">
        <span>9. Martial status</span>
        <div class="flex flex-wrap">
          <div>
            <input
              type="checkbox"
              name="single"
              v-model="applicationData.martialStatus.single"
            />
            <label for="single">Single</label>
          </div>
          <div>
            <input
              type="checkbox"
              name="married"
              v-model="applicationData.martialStatus.married"
            />
            <label for="married">Married</label>
          </div>
          <div>
            <input
              type="checkbox"
              name="separated"
              v-model="applicationData.martialStatus.separated"
            />
            <label for="separated">Separated</label>
          </div>
          <div>
            <input
              type="checkbox"
              name="divorced"
              v-model="applicationData.martialStatus.divorced"
            />
            <label for="divorced">Divorced</label>
          </div>
          <div>
            <input
              type="checkbox"
              name="widow"
              v-model="applicationData.martialStatus.widow"
            />
            <label for="widow">Widow(ed)</label>
          </div>
          <div>
            <input
              type="checkbox"
              name="otherVallue"
              v-model="applicationData.martialStatus.other"
            />
            <label for="other">Other</label>
          </div>
          <div>
            <input
              type="input"
              name="otherValue"
              v-model="applicationData.martialStatus.otherValue"
            />
            <label for="otherValue">(please specify)</label>
          </div>
        </div>
      </div>
    </div>

    <!-- 10,11 -->
    <div class="flex flex-col bg-gray-100">
      <span
        >10. In the case of minors: Surname, first name, address (if different
        from applicant's) and nationality of parental authority/legal
        guardian</span
      >
      <input class="w-full" type="text" v-model="applicationData.minorsData" />
    </div>
    <div class="flex flex-col bg-gray-100">
      <span>11. National identity number, where applicable</span>
      <input
        class="w-full"
        type="text"
        v-model="applicationData.nationalIdentityNumber"
      />
    </div>

    <!-- 12 -->
    <div class="flex flex-col w-full bg-gray-100">
      <span>12. Type of travel document</span>
      <div class="flex flex-wrap">
        <div>
          <input
            type="checkbox"
            name="ordinary"
            v-model="applicationData.travelDocumentType.ordinary"
          />
          <label for="ordinary">Ordinary passport</label>
        </div>
        <div>
          <input
            type="checkbox"
            name="diplomatic"
            v-model="applicationData.travelDocumentType.diplomatic"
          />
          <label for="diplomatic">Diplomatic passport</label>
        </div>
        <div>
          <input
            type="checkbox"
            name="service"
            v-model="applicationData.travelDocumentType.service"
          />
          <label for="service">Service passport</label>
        </div>
        <div>
          <input
            type="checkbox"
            name="official"
            v-model="applicationData.travelDocumentType.official"
          />
          <label for="official">Official passport</label>
        </div>
        <div>
          <input
            type="checkbox"
            name="special"
            v-model="applicationData.travelDocumentType.special"
          />
          <label for="special">Special passport</label>
        </div>
        <div>
          <input
            type="checkbox"
            name="other"
            v-model="applicationData.travelDocumentType.other"
          />
          <label for="other">Other travel document</label>
        </div>
        <div>
          <input
            class="w-full"
            type="input"
            name="otherValue"
            v-model="applicationData.travelDocumentType.otherValue"
          />
          <label for="otherValue">(please specify)</label>
        </div>
      </div>
    </div>

    <!-- 13,14,15,16 -->
    <div class="flex w-full">
      <div class="flex flex-col bg-gray-100 w-full">
        <span>13. Number of travel document</span>
        <input
          class="w-full"
          type="text"
          v-model="applicationData.travleDocumentNumber"
        />
      </div>
      <div class="flex flex-col bg-gray-100 w-full">
        <span>14. Date of issue</span>
        <input
          class="w-full"
          type="date"
          v-model="applicationData.travelDocumentIssuindDate"
        />
      </div>
      <div class="flex flex-col bg-gray-100 w-full">
        <span>15. Valid until</span>
        <input
          class="w-full"
          type="date"
          v-model="applicationData.travelDocumentExpirationDate"
        />
      </div>
      <div class="flex flex-col bg-gray-100 w-full">
        <span>16. Issued by</span>
        <input
          class="w-full"
          type="text"
          v-model="applicationData.travelDocumentIssuedBy"
        />
      </div>
    </div>

    <!-- 17 -->
    <div class="flex w-full">
      <div class="flex flex-col bg-gray-100 w-full">
        <span>17. Applicant's home address</span>
        <input class="w-full" type="text" v-model="applicationData.address" />
      </div>
      <div class="flex flex-col bg-gray-100 w-full">
        <span>e-mail</span>
        <input class="w-full" type="email" v-model="applicationData.email" />
      </div>
      <div class="flex flex-col bg-gray-100 w-full">
        <span>Phone mnumber</span>
        <input class="w-full" type="text" v-model="applicationData.phone" />
      </div>
    </div>

    <!-- 18 -->
    <div class="flex w-full">
      <div class="flex flex-col w-full bg-gray-100">
        <span
          >18. Residence in a country other than the country of current
          nationality</span
        >
        <div class="flex">
          <div>
            <input
              type="checkbox"
              name="no"
              v-model="applicationData.otherResidence.no"
            />
            <label for="no">No</label>
          </div>
          <div>
            <input
              type="checkbox"
              name="yes"
              v-model="applicationData.otherResidence.yes"
            />
            <label for="yes">Yes</label>
          </div>
          <div>
            <input
              class="w-full"
              type="input"
              name="documentName"
              v-model="applicationData.otherResidence.documentName"
            />
            <label for="documentName">Residence permit or equivalent</label>
          </div>
          <div>
            <input
              class="w-full"
              type="input"
              name="documentNumber"
              v-model="applicationData.otherResidence.documentNumber"
            />
            <label for="documentNumber">No.</label>
          </div>
          <div>
            <input
              class="w-full"
              type="date"
              name="documentExpiration"
              v-model="applicationData.otherResidence.expirationDate"
            />
            <label for="documentExpiration">Valid until</label>
          </div>
        </div>
      </div>
    </div>

    <!-- 19 -->
    <div class="flex flex-col bg-gray-100">
      <span>* 19. Current occupation</span>
      <input
        class="w-full"
        type="text"
        v-model="applicationData.currentOccupation"
      />
    </div>

    <!-- isStudent pivot -->
    <div class="flex flex-col bg-gray-100">
      <div>
        <input
          type="checkbox"
          name="isStudent"
          v-model="applicationData.isStudent"
        />
        <label for="isStudent">Student</label>
      </div>
    </div>

    <!-- 20 -->
    <div class="flex flex-col bg-gray-100">
      <span>* 20. Employer and employer's address and telephone number</span>
      <div class="flex">
        <div class="w-full">
          <input
            class="w-full"
            type="text"
            name="employerFullname"
            v-model="applicationData.employer.fullName"
          />
          <label for="employerFullname">Full name</label>
        </div>
        <div class="w-full">
          <input
            class="w-full"
            type="text"
            name="employerAddress"
            v-model="applicationData.employer.address"
          />
          <label for="employerAddress">Address</label>
        </div>
        <div class="w-full">
          <input
            class="w-full"
            type="text"
            name="employerPhone"
            v-model="applicationData.employer.phone"
          />
          <label for="employerPhone">Phone number</label>
        </div>
      </div>

      <!-- case student -->
      <div class="flex">
        <div class="w-full">
          <input
            class="w-full"
            type="text"
            name="establishmentName"
            v-model="applicationData.educatinoalEstablishment.name"
          />
          <label for="establishmentName">Educational establishment name</label>
        </div>
        <div class="w-full">
          <input
            class="w-full"
            type="text"
            name="establishmentAddress"
            v-model="applicationData.educatinoalEstablishment.address"
          />
          <label for="establishmentAddress"
            >Educational establishment address</label
          >
        </div>
      </div>
    </div>

    <!-- 21 -->
    <div class="flex flex-col w-full bg-gray-100">
      <span>21. Main purpose(s) of the journey</span>
      <div class="flex flex-wrap">
        <div>
          <input
            type="checkbox"
            name="tourism"
            v-model="applicationData.travelPurpose.tourism"
          />
          <label for="tourism">Tourism</label>
        </div>
        <div>
          <input
            type="checkbox"
            name="business"
            v-model="applicationData.travelPurpose.business"
          />
          <label for="business">Business</label>
        </div>
        <div>
          <input
            type="checkbox"
            name="visit"
            v-model="applicationData.travelPurpose.visit"
          />
          <label for="visit">Visiting family or friends</label>
        </div>
        <div>
          <input
            type="checkbox"
            name="cultural"
            v-model="applicationData.travelPurpose.cultural"
          />
          <label for="cultural">Cultural</label>
        </div>
        <div>
          <input
            type="checkbox"
            name="sports"
            v-model="applicationData.travelPurpose.sports"
          />
          <label for="sports">Sports</label>
        </div>
        <div>
          <input
            type="checkbox"
            name="medical"
            v-model="applicationData.travelPurpose.medical"
          />
          <label for="medical">Medical reasons</label>
        </div>
        <div>
          <input
            type="checkbox"
            name="study"
            v-model="applicationData.travelPurpose.study"
          />
          <label for="study">Study</label>
        </div>
        <div>
          <input
            type="checkbox"
            name="transit"
            v-model="applicationData.travelPurpose.transit"
          />
          <label for="transit">Transit</label>
        </div>
        <div>
          <input
            type="checkbox"
            name="airportTransit"
            v-model="applicationData.travelPurpose.airportTransit"
          />
          <label for="airportTransit">Airport transit</label>
        </div>
        <div>
          <input
            type="checkbox"
            name="other"
            v-model="applicationData.travelPurpose.other"
          />
          <label for="other">Other</label>
        </div>
        <div>
          <input
            class="w-full"
            type="input"
            name="otherValue"
            v-model="applicationData.travelPurpose.otherValue"
          />
          <label for="otherValue">(please specify)</label>
        </div>
      </div>
    </div>

    <!-- 22,23 -->
    <div class="flex w-full">
      <div class="flex flex-col bg-gray-100 w-full">
        <span>22. Member State(s) of destination</span>
        <input
          class="w-full"
          type="input"
          v-model="applicationData.memberDestinationState"
        />
      </div>
      <div class="flex flex-col bg-gray-100 w-full">
        <span>23. Member State of first entry</span>
        <input
          class="w-full"
          type="input"
          v-model="applicationData.memberFirstEntryState"
        />
      </div>
    </div>

    <!-- 24,25 -->
    <div class="flex w-full">
      <div class="flex flex-col bg-gray-100 w-full">
        <span>24. Number of entries requested</span>
        <div class="flex flex-wrap">
          <div>
            <input
              type="checkbox"
              name="singleEntry"
              v-model="applicationData.entriesNumber.single"
            />
            <label for="singleEntry">Single entry</label>
          </div>
          <div>
            <input
              type="checkbox"
              name="doubleEntry"
              v-model="applicationData.entriesNumber.double"
            />
            <label for="doubleEntry">Two entries</label>
          </div>
          <div>
            <input
              type="checkbox"
              name="multiple"
              v-model="applicationData.entriesNumber.multiple"
            />
            <label for="multiple">Multiple entries</label>
          </div>
        </div>
      </div>
      <div class="flex flex-col bg-gray-100 w-full">
        <span>25. Duration of the intended stay or transit</span>
        <input
          class="w-full"
          type="number"
          v-model="applicationData.duration"
        />
      </div>
    </div>

    <!-- PAGE 2 -->

    <!-- 26 -->
    <div class="flex w-full">
      <div class="flex flex-col w-full bg-gray-100">
        <span>26. Schengen visas issued during the past three years</span>
        <div class="flex">
          <div>
            <input
              type="checkbox"
              name="no"
              v-model="applicationData.previousVisas.no"
            />
            <label for="no">No</label>
          </div>
          <div>
            <input
              type="checkbox"
              name="yes"
              v-model="applicationData.previousVisas.yes"
            />
            <label for="yes">Yes</label>
          </div>
          <div class="w-full">
            <label for="issuedOn">Valid from</label>
            <input
              class="w-full"
              type="date"
              name="issuedOn"
              v-model="applicationData.previousVisas.issuedOn"
            />
          </div>
          <div class="w-full">
            <label for="expiresOn">to</label>
            <input
              class="w-full"
              type="date"
              name="expiresOn"
              v-model="applicationData.previousVisas.expiresOn"
            />
          </div>
        </div>
      </div>
    </div>

    <!-- 27 -->
    <div class="flex w-full">
      <div class="flex flex-col w-full bg-gray-100">
        <span
          >27.Fingerprints collected previously for the purpose of applying for
          a Schengen visa</span
        >
        <div class="flex">
          <div>
            <input
              type="checkbox"
              name="no"
              v-model="applicationData.fingerprintsCollected.no"
            />
            <label for="no">No</label>
          </div>
          <div>
            <input
              type="checkbox"
              name="yes"
              v-model="applicationData.fingerprintsCollected.yes"
            />
            <label for="yes">Yes</label>
          </div>
          <div>
            <label for="issuedOn">Date if known</label>
            <input
              class="w-full"
              type="date"
              name="issuedOn"
              v-model="applicationData.fingerprintsCollected.collectedOn"
            />
          </div>
        </div>
      </div>
    </div>

    <!-- 28 -->
    <div class="flex flex-col bg-gray-100">
      <span
        >28. Entry permit for the final country of destination, where
        applicable</span
      >
      <div class="flex">
        <div class="w-full">
          <label for="issuedBy">Issued by</label>
          <input
            class="w-full"
            type="input"
            name="issuedBy"
            v-model="applicationData.finalCountryEntry.issuedBy"
          />
        </div>
        <div class="w-full">
          <label for="validFrom">Valid from</label>
          <input
            class="w-full"
            type="date"
            name="validFrom"
            v-model="applicationData.finalCountryEntry.issuedOn"
          />
        </div>
        <div class="w-full">
          <label for="expiresOn">to</label>
          <input
            class="w-full"
            type="date"
            name="expiresOn"
            v-model="applicationData.finalCountryEntry.expiresOn"
          />
        </div>
      </div>
    </div>

    <!-- 29,30 -->
    <div class="flex w-full bg-gray-100">
      <div>
        <span>29. Intended date of arrival in the Schengen area</span>
        <input class="w-full" type="date" v-model="dateOfArrival" />
      </div>
      <div>
        <span> 30. Intended date of departure from the Schengen area </span>
        <input class="w-full" type="date" v-model="dateOfDeparture" />
      </div>
    </div>

    <!-- 31 -->
    <div class="flex flex-col w-full bg-gray-100">
      <span
        >* 31. Surname and first name of the inviting person(s) in the Member
        State(s)</span
      >
      <div class="flex">
        <div class="w-full">
          <label for="firstName">First name</label>
          <input
            class="w-full"
            type="text"
            name="firstName"
            v-model="applicationData.invitingPerson.firstName"
          />
        </div>
        <div class="w-full">
          <label for="surname">Surname</label>
          <input
            class="w-full"
            type="text"
            name="surname"
            v-model="applicationData.invitingPerson.surname"
          />
        </div>
        <div class="w-full">
          <label for="address">Address</label>
          <input
            class="w-full"
            type="text"
            name="address"
            v-model="applicationData.invitingPerson.address"
          />
        </div>
        <div class="w-full">
          <label for="email">Email</label>
          <input
            class="w-full"
            type="email"
            name="email"
            v-model="applicationData.invitingPerson.email"
          />
        </div>
      </div>

      <!-- accomodation data -->

      <span
        >If not applicable, name of hotel(s) or temporary accommodation(s) in
        the Member State(s)</span
      >
      <div class="flex">
        <div class="w-full">
          <label for="address">Address</label>
          <input
            class="w-full"
            type="text"
            name="address"
            v-model="applicationData.accomodation.address"
          />
        </div>
        <div class="w-full">
          <label for="email">Email</label>
          <input
            class="w-full"
            type="email"
            name="email"
            v-model="applicationData.accomodation.email"
          />
        </div>
      </div>
    </div>

    <!-- 32 -->
    <div class="flex flex-col w-full bg-gray-100">
      <span>*32. Name and address of inviting company/organisation</span>
      <div class="flex">
        <div class="w-full">
          <label for="name">Name</label>
          <input
            class="w-full"
            type="text"
            name="name"
            v-model="applicationData.invitingCompany.name"
          />
        </div>
        <div class="w-full">
          <label for="address">Address</label>
          <input
            class="w-full"
            type="text"
            name="address"
            v-model="applicationData.invitingCompany.address"
          />
        </div>
        <div class="w-full">
          <label for="phone">Phone number</label>
          <input
            class="w-full"
            type="text"
            name="phone"
            v-model="applicationData.invitingCompany.phone"
          />
        </div>
        <div class="w-full">
          <label for="fax">Fax</label>
          <input
            class="w-full"
            type="text"
            name="fax"
            v-model="applicationData.invitingCompany.fax"
          />
        </div>
      </div>
    </div>

    <!-- 33 -->
    <!-- <div class="flex w-full bg-gray-100"></div> -->

    <!-- 34 -->
    <!-- <div class="flex w-full bg-gray-100"></div> -->

    <!-- 35 -->
    <!-- <div class="flex w-full bg-gray-100"></div> -->

    <!-- 36 -->
    <!-- <div class="flex w-full bg-gray-100"></div> -->
  </div>
</template>

<script>
export default {
  name: "MainView",
  data() {
    return {
      applicationData: {
        surname: "",
        surnameAtBirth: "",
        firstName: "",
        dateOfBirth: "", // type date
        placeOfBirth: "",
        countryOfBirth: "",
        currentNationality: "",
        nationalityAtBirth: "", // optional
        sex: {
          male: false,
          female: false,
        },
        martialStatus: {
          single: false,
          married: false,
          separated: false,
          divorced: false,
          widow: false,
          other: false,
          otherValue: "",
        },
        minorsData: "",
        nationalIdentityNumber: "",
        travelDocumentType: {
          ordinary: false,
          diplomatic: false,
          service: false,
          official: false,
          special: false,
          other: false,
          otherValue: "",
        },
        travleDocumentNumber: "",
        travelDocumentIssuindDate: "", // type date
        travelDocumentExpirationDate: "", // type date
        travelDocumentIssuedBy: "",
        address: "",
        email: "", // type email
        phone: "",
        otherResidence: {
          no: false,
          yes: false,
          documentName: "",
          documentNumber: "",
          expirationDate: "", // type date
        },
        isStudent: false, // pivoting variable
        currentOccupation: "",
        employer: {
          fullName: "",
          address: "",
          phone: "",
        },
        educatinoalEstablishment: {
          name: "",
          address: "",
        },
        travelPurpose: {
          tourism: false,
          business: false,
          visit: false,
          cultural: false,
          sports: false,
          official: false,
          medical: false,
          study: false,
          transit: false,
          airportTransit: false,
          other: false,
          otherValue: "",
        },
        memberDestinationState: "",
        memberFirstEntryState: "",
        entriesNumber: {
          single: false,
          double: false,
          multiple: false,
        },
        duration: 0, // type number

        // Page 2

        previousVisas: {
          no: false,
          yes: false,
          issuedOn: "", // type date
          espiresOn: "", // type date
        },
        fingerprintsCollected: {
          no: false,
          yes: false,
          collectedOn: "", // type date *optional if known
        },
        finalCountryEntry: {
          issuedBy: "",
          issuedOn: "", // type date
          expiresOn: "", // type date
        },
        dateOfArrival: "", // type date
        dateOfDeparture: "", // type date

        // --- Relies on the tripPurpose 'visit'
        invitingPerson: {
          firstName: "",
          surname: "",
          address: "",
          email: "", // type email
        },
        accomodation: {
          address: "",
          email: "",
        },
        invitingCompany: {
          name: "",
          address: "",
          phone: "",
          fax: "",
        },
        // companyReference: {
        //   firstName: "",
        //   surname: "",
        //   address: "",
        //   phone: "",
        //   email: "",
        // },
        // costsCoverage: {
        //   applicant: false,
        //   applicantTypes: {
        //     cash: false,
        //     check: false,
        //     creditCard: false,
        //     prepaidAccommodation: false,
        //     prepaidTransport: false,
        //     other: false,
        //     otherValue: "",
        //   },
        //   sponsor: false,
        //   referredPreviously: false,
        //   otherSponsors: false,
        //   otherSponsorsValue: "",
        //   sponsorTypes: {
        //     cash: false,
        //     accomodation: false,
        //     allCovered: false,
        //     prepaidTransport: false,
        //     other: false,
        //     otherValue: "",
        //   },
        //   familyMember: {
        //     surname: "",
        //     firstName: "",
        //     dateOfBirth: "", // type date
        //     nationality: "",
        //     documentNumber: "",
        //   },
        //   relationshipType: {
        //     spouse: false,
        //     child: false,
        //     grandchild: false,
        //     dependent: false,
        //   },
        //   place: "", // *shared info in two sections
        //   date: "", // type date *shared info in two sections
        //   visaFeeAcceptance: false, // mandatory
        //   insuranceAccepance: false, // mandatory
        //   personalDataProcessingAcceptance: false, // mandatory
        //   finalAcceptance: false, // mandatory
        // },
      },
    };
  },
};
</script>
