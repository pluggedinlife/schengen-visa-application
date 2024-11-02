<template>
  <div id="target" ref="target">
    <div class="flex h-full flex-1 flex-col space-y-8 p-8">
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
      <div
        class="flex flex-col text-xs space-y-2 border-l border-gray-600 pl-2"
      >
        <span>&#9888; Important</span>
        <span>
          The fields marked with * shall not be filled in by family members of
          EU, EEA or CH citizens (spouse, child or dependent ascendant) while
          exercising their right to free movement. Family members of EU, EEA or
          CH citizens shall present documents to prove this relationship and
          fill in fields no 34 and 35. (x) Fields 1-3 shall be filled in in
          accordance with the data in the travel document.
        </span>
      </div>

      <!-- 1,2,3 -->
      <InputText
        label="1. Surname (family name) (x)"
        v-model="applicationData.surname"
        uid="lastName"
      />
      <InputText
        label="2. Surname at birth (Former family name(s)) (x)"
        v-model="applicationData.surnameAtBirth"
        uid="surnameAtBirth"
      />
      <InputText
        label="3. First name(s) (Given name(s)) (x)"
        v-model="applicationData.firstName"
        uid="firstName"
      />

      <!-- 4,5,6,7 -->
      <div class="flex w-full">
        <InputDate
          label="4. Date of birth (day-month-year)"
          v-model="applicationData.dateOfBirth"
          uid="dateOfBirth"
        />
        <div class="flex flex-col w-full">
          <InputText
            label="5. Place of birth"
            v-model="applicationData.placeOfBirth"
            uid="placeOfBirth"
          />
          <InputText
            label="6. Country of birth"
            v-model="applicationData.countryOfBirth"
            uid="countryOfBirth"
          />
        </div>
        <div class="flex flex-col w-full">
          <InputText
            label="7. Current nationality"
            v-model="applicationData.currentNationality"
            uid="currentNationality"
          />
          <InputText
            label="Nationality at birth (if different)"
            v-model="applicationData.nationalityAtBirth"
            uid="nationalityAtBirth"
          />
        </div>
      </div>

      <!-- 8,9 -->
      <div class="flex w-full">
        <div class="flex flex-col w-full">
          <InputSelect
            label="8. Sex"
            v-model="applicationData.sex"
            uid="sex"
            name="sex"
            :options="sexOptions"
          />
        </div>

        <div class="flex flex-col w-full">
          <InputSelect
            label="9. Martial status"
            v-model="applicationData.martialStatus"
            uid="martialStatus"
            name="martialStatus"
            :options="martialStatusOptions"
          />
          <InputText
            v-if="isMartialStatusUnspecified"
            label="Please specify"
            v-model="applicationData.martialStatusOtherValue"
            uid="martialStatusOtherValue"
          />
        </div>
      </div>

      <!-- 10,11 -->
      <div class="flex flex-col">
        <InputText
          label="10. In the case of minors: Surname, first name, address (if different
          from applicant's) and nationality of parental authority/legal
          guardian"
          v-model="applicationData.minorsData"
          uid="minorsData"
        />
      </div>
      <div class="flex flex-col">
        <InputText
          label="11. National identity number, where applicable"
          v-model="applicationData.nationalIdentityNumber"
          uid="nationalIdentityNumber"
        />
      </div>

      <!-- 12 -->
      <div class="flex flex-col w-full">
        <InputSelect
          label="12. Type of travel document"
          v-model="applicationData.travelDocumentType"
          uid="travelDocumentType"
          name="travelDocumentType"
          :options="travelDocumentTypeOptions"
        />
        <InputText
          v-if="isTravelDocumentTypeUnspecified"
          label="Please specify"
          v-model="applicationData.travelDocumentTypeOtherValue"
          uid="travelDocumentTypeOtherValue"
        />
      </div>

      <!-- 13,14,15,16 -->
      <div class="flex w-full">
        <div class="flex flex-col w-full">
          <InputText
            label="13. Number of travel document"
            v-model="applicationData.travelDocumentNumber"
            uid="travelDocumentNumber"
          />
        </div>
        <div class="flex flex-col w-full">
          <InputDate
            label="14. Date of issue"
            v-model="applicationData.travelDocumentIssuedDate"
            uid="travelDocumentIssuedDate"
          />
        </div>
        <div class="flex flex-col w-full">
          <InputDate
            label="15. Valid until"
            v-model="applicationData.travelDocumentExpirationDate"
            uid="travelDocumentExpirationDate"
          />
        </div>
        <div class="flex flex-col w-full">
          <InputText
            label="16. Issued by"
            v-model="applicationData.travelDocumentIssuedBy"
            uid="travelDocumentIssuedBy"
          />
        </div>
      </div>

      <!-- 17 -->
      <div class="flex w-full">
        <div class="flex flex-col w-full">
          <InputText
            label="17. Applicant's home address"
            v-model="applicationData.address"
            uid="address"
          />
        </div>
        <div class="flex flex-col w-full">
          <InputText
            label="E-mail"
            v-model="applicationData.email"
            uid="email"
            type-field="email"
          />
        </div>
        <div class="flex flex-col w-full">
          <InputText
            label="Phone number"
            v-model="applicationData.phone"
            uid="phone"
          />
        </div>
      </div>

      <!-- 18 -->
      <div class="flex w-full">
        <InputSelect
          label="18. Residence in a country other than the country of current
          nationality"
          v-model="applicationData.otherResidence"
          uid="otherResidence"
          name="otherResidence"
          :options="yesNoOptions"
        />

        <div class="flex" v-if="applicationData.otherResidence == 'yes'">
          <InputText
            label="Residence permit or equivalent"
            v-model="applicationData.otherResidenceDocumentName"
            uid="otherResidenceDocumentName"
          />

          <InputText
            label="Document number"
            v-model="applicationData.otherResidenceDocumentNumber"
            uid="otherResidenceDocumentNumber"
          />

          <InputDate
            label="Valid until"
            v-model="applicationData.otherResidenceExpirationDate"
            uid="otherResidenceExpirationDate"
          />
        </div>
      </div>

      <!-- 19, 20 -->
      <div class="flex flex-col w-full">
        <InputSelect
          label="* 19-20. Current occupation (student or not). Employer and employer's address and telephone number. For students, name and
address of educational establishment."
          v-model="applicationData.isStudent"
          uid="isStudent"
          name="isStudent"
          :options="yesNoOptions"
        />
        <!-- IF STUDENT -->
        <div class="flex w-full" v-if="applicationData.isStudent == 'yes'">
          <div class="flex flex-col w-full">
            <InputText
              label="Current occupation"
              v-model="applicationData.currentOccupation"
              uid="currentOccupation"
            />
          </div>
          <div class="flex flex-col w-full">
            <InputText
              label="Education establishment's name"
              v-model="applicationData.educatinoalEstablishmentName"
              uid="educatinoalEstablishmentName"
            />
          </div>
          <div class="flex flex-col w-full">
            <InputText
              label="Education establishment's address"
              v-model="applicationData.educatinoalEstablishmentAddress"
              uid="educatinoalEstablishmentAddress"
            />
          </div>
        </div>

        <!-- IF NOT STUDENT -->
        <div class="flex w-full" v-else>
          <div class="flex flex-col w-full">
            <InputText
              label="Current occupation"
              v-model="applicationData.currentOccupation"
              uid="currentOccupation"
            />
          </div>
          <div class="flex flex-col w-full">
            <InputText
              label="Employer's full name"
              v-model="applicationData.employerFullName"
              uid="employerFullName"
            />
          </div>
          <div class="flex flex-col w-full">
            <InputText
              label="Employer's address"
              v-model="applicationData.employerAddress"
              uid="employerAddress"
            />
          </div>
          <div class="flex flex-col w-full">
            <InputText
              label="Employer's phone"
              v-model="applicationData.employerPhone"
              uid="employerPhone"
            />
          </div>
        </div>
      </div>

      <!-- 21 -->
      <div class="flex flex-col w-full">
        <InputSelect
          label="21. Main purpose(s) of the journey"
          v-model="applicationData.travelPurpose"
          uid="travelPurpose"
          name="travelPurpose"
          :options="travelPurposeOptions"
        />
        <InputText
          v-if="applicationData.travelPurpose == 'other'"
          label="Please specify"
          v-model="applicationData.travelPurposeOtherValue"
          uid="travelPurposeOtherValue"
        />
      </div>

      <!-- 22,23 -->
      <div class="flex w-full">
        <div class="flex flex-col w-full">
          <InputText
            label="22. Member State(s) of destination"
            v-model="applicationData.memberDestinationState"
            uid="memberDestinationState"
          />
        </div>
        <div class="flex flex-col w-full">
          <InputText
            label="23. Member State of first entry"
            v-model="applicationData.memberStateFirstEntry"
            uid="memberStateFirstEntry"
          />
        </div>
      </div>

      <!-- 24,25 -->
      <div class="flex w-full">
        <div class="flex flex-col w-full">
          <InputSelect
            label="24. Number of entries requested"
            v-model="applicationData.entriesRequested"
            uid="entriesRequested"
            name="entriesRequested"
            :options="entriesOptions"
          />
        </div>
        <div class="flex flex-col w-full">
          <InputText
            label="25. Duration of the intended stay or transit"
            v-model="applicationData.duration"
            uid="duration"
            type-field="number"
          />
        </div>
      </div>

      <!-- PAGE 2 -->

      <!-- 26 -->
      <!-- <div class="flex w-full">
        <div class="flex flex-col w-full ">
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
      </div> -->

      <!-- 27 -->
      <!-- <div class="flex w-full">
        <div class="flex flex-col w-full ">
          <span
            >27.Fingerprints collected previously for the purpose of applying
            for a Schengen visa</span
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
      </div> -->

      <!-- 28 -->
      <!-- <div class="flex flex-col ">
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
      </div> -->

      <!-- 29,30 -->
      <!-- <div class="flex w-full ">
        <div>
          <span>29. Intended date of arrival in the Schengen area</span>
          <input
            class="w-full"
            type="date"
            v-model="applicationData.dateOfArrival"
          />
        </div>
        <div>
          <span> 30. Intended date of departure from the Schengen area </span>
          <input
            class="w-full"
            type="date"
            v-model="applicationData.dateOfDeparture"
          />
        </div>
      </div> -->

      <!-- 31 -->
      <!-- <div class="flex flex-col w-full ">
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
      </div> -->

      <!-- 32 -->
      <!-- <div class="flex flex-col w-full ">
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
        </div> -->

      <!-- Company reference -->

      <!--   <span
          >Surname, first name, address, telephone, telefax, and e-mail address
          of contact person in company/organisation</span
        >
        <div class="flex">
          <div class="w-full">
            <label for="surname">Surname</label>
            <input
              class="w-full"
              type="text"
              name="surname"
              v-model="applicationData.companyReference.surname"
            />
          </div>
          <div class="w-full">
            <label for="firstName">First name</label>
            <input
              class="w-full"
              type="text"
              name="firstName"
              v-model="applicationData.companyReference.firstName"
            />
          </div>
          <div class="w-full">
            <label for="address">Address</label>
            <input
              class="w-full"
              type="text"
              name="address"
              v-model="applicationData.companyReference.address"
            />
          </div>
          <div class="w-full">
            <label for="phone">Phone</label>
            <input
              class="w-full"
              type="text"
              name="phone"
              v-model="applicationData.companyReference.phone"
            />
          </div>
          <div class="w-full">
            <label for="fax">Fax</label>
            <input
              class="w-full"
              type="text"
              name="fax"
              v-model="applicationData.companyReference.fax"
            />
          </div>
          <div class="w-full">
            <label for="email">E-mail</label>
            <input
              class="w-full"
              type="email"
              name="email"
              v-model="applicationData.companyReference.email"
            />
          </div>
        </div>
      </div> -->

      <!-- 33 -->
      <!-- <div class="flex flex-col w-full ">
        <span
          >*33. Cost of travelling and living during the applicant's stay is
          covered</span
        >
        <div class="flex">
          <div class="w-full flex flex-col">
            <div class="mb-4">
              <input
                type="checkbox"
                name="applicant"
                v-model="applicationData.costsCoverage.applicant"
              />
              <label for="applicant">By the applicant himself/herself</label>
            </div>

            <span>Means of support</span>
            <div>
              <input
                type="checkbox"
                name="cash"
                v-model="applicationData.costsCoverage.applicantTypes.cash"
              />
              <label for="cash">Cash</label>
            </div>
            <div>
              <input
                type="checkbox"
                name="checks"
                v-model="applicationData.costsCoverage.applicantTypes.checks"
              />
              <label for="checks">Traveller's cheques</label>
            </div>
            <div>
              <input
                type="checkbox"
                name="creditCard"
                v-model="
                  applicationData.costsCoverage.applicantTypes.creditCard
                "
              />
              <label for="creditCard">Credit card</label>
            </div>
            <div>
              <input
                type="checkbox"
                name="accomodation"
                v-model="
                  applicationData.costsCoverage.applicantTypes
                    .prepaidAccommodation
                "
              />
              <label for="accomodation">Pre-paid accommodation</label>
            </div>
            <div>
              <input
                type="checkbox"
                name="transport"
                v-model="
                  applicationData.costsCoverage.applicantTypes.prepaidTransport
                "
              />
              <label for="transport">Pre-paid transport</label>
            </div>
            <div>
              <input
                type="checkbox"
                name="other"
                v-model="applicationData.costsCoverage.applicantTypes.other"
              />
              <label for="other">Other</label>
            </div>
            <div>
              <label for="otherValue">(please specify)</label>
              <input
                class="w-full"
                type="input"
                name="otherValue"
                v-model="
                  applicationData.costsCoverage.applicantTypes.otherValue
                "
              />
            </div>
          </div>

          <div class="w-full">
            <div class="mb-4">
              <input
                type="checkbox"
                name="sponsor"
                v-model="applicationData.costsCoverage.sponsor"
              />
              <label for="sponsor"
                >by a sponsor (host, company, organisation), please
                specify</label
              >
            </div>
            <div>
              <input
                type="checkbox"
                name="referredSponsor"
                v-model="applicationData.costsCoverage.referredPreviously"
              />
              <label for="referredSponsor">referred to in field 31 or 32</label>
            </div>
            <div>
              <input
                type="checkbox"
                name="other"
                v-model="applicationData.costsCoverage.otherSponsors"
              />
              <label for="other">Other</label>
            </div>
            <div class="mb-4">
              <label for="otherSponsorsValue">(please specify)</label>
              <input
                class="w-full"
                type="input"
                name="otherSponsorsValue"
                v-model="applicationData.costsCoverage.otherSponsorsValue"
              />
            </div>

            <span>Means of support</span>
            <div>
              <input
                type="checkbox"
                name="cash"
                v-model="applicationData.costsCoverage.sponsorTypes.cash"
              />
              <label for="cash">Cash</label>
            </div>
            <div>
              <input
                type="checkbox"
                name="accommodation"
                v-model="
                  applicationData.costsCoverage.sponsorTypes.accommodation
                "
              />
              <label for="accommodation">Accommodation provided</label>
            </div>
            <div>
              <input
                type="checkbox"
                name="allCovered"
                v-model="applicationData.costsCoverage.sponsorTypes.allCovered"
              />
              <label for="allCovered"
                >All expenses covered during the stay</label
              >
            </div>
            <div>
              <input
                type="checkbox"
                name="prepaidTransport"
                v-model="
                  applicationData.costsCoverage.sponsorTypes.prepaidTransport
                "
              />
              <label for="prepaidTransport">Pre-paid transport</label>
            </div>
            <div>
              <input
                type="checkbox"
                name="other"
                v-model="applicationData.costsCoverage.sponsorTypes.other"
              />
              <label for="other">Other</label>
            </div>
            <div>
              <label for="otherValue">(please specify)</label>
              <input
                class="w-full"
                type="input"
                name="otherValue"
                v-model="applicationData.costsCoverage.sponsorTypes.otherValue"
              />
            </div>
          </div>
        </div>
      </div> -->

      <!-- 34 -->
      <!-- <div class="flex flex-col w-full ">
        <span
          >34. Personal data of the family member who is an EU, EEA or CH
          citizen</span
        >
        <div class="flex">
          <div class="w-full flex flex-col">
            <label for="surname">Surname</label>
            <input
              type="text"
              name="surname"
              v-model="applicationData.familyMember.surname"
            />
          </div>
          <div class="w-full flex flex-col">
            <label for="firstName">First name</label>
            <input
              type="text"
              name="firstName"
              v-model="applicationData.familyMember.firstName"
            />
          </div>
        </div>
        <div class="flex">
          <div class="w-full flex flex-col">
            <label for="birthDate">Date of birth</label>
            <input
              type="date"
              name="birthDate"
              v-model="applicationData.familyMember.dateOfBirth"
            />
          </div>
          <div class="w-full flex flex-col">
            <label for="nationality">Nationality</label>
            <input
              type="text"
              name="nationality"
              v-model="applicationData.familyMember.nationality"
            />
          </div>
          <div class="w-full flex flex-col">
            <label for="documentNumber"
              >Number of travel document or ID card</label
            >
            <input
              type="text"
              name="documentNumber"
              v-model="applicationData.familyMember.documentNumber"
            />
          </div>
        </div>
      </div> -->

      <!-- 35 -->
      <!-- <div class="flex flex-col w-full ">
        <span>35. Family relationship with an EU, EEA or CH citizen</span>
        <div class="flex">
          <div class="w-full">
            <input
              type="checkbox"
              name="spouse"
              v-model="applicationData.relationshipType.spouse"
            />
            <label for="spouse">Spouse</label>
          </div>
          <div class="w-full">
            <input
              type="checkbox"
              name="child"
              v-model="applicationData.relationshipType.grandchild"
            />
            <label for="child">Child</label>
          </div>
          <div class="w-full">
            <input
              type="checkbox"
              name="grandchild"
              v-model="applicationData.relationshipType.child"
            />
            <label for="grandchild">Grandchild</label>
          </div>
          <div class="w-full">
            <input
              type="checkbox"
              name="dependent"
              v-model="applicationData.relationshipType.dependent"
            />
            <label for="dependent">Dependent ascendant</label>
          </div>
        </div>
      </div> -->

      <!-- 36 -->
      <!-- <div class="flex w-full ">
        <div class="w-full flex flex-col">
          <div class="w-full">
            <label for="place">Place</label>
            <input
              class="w-full"
              type="input"
              name="place"
              v-model="applicationData.place"
            />
          </div>
          <div class="w-full">
            <label for="date">Date</label>
            <input
              class="w-full"
              type="date"
              name="date"
              v-model="applicationData.date"
            />
          </div>
        </div>
        <div class="w-full">
          <span>Signature</span>
        </div>
      </div> -->

      <!-- Acceptance area -->
      <!-- <div class="flex flex-col w-full space-y-4 ">
        <div class="w-full flex-col">
          <input type="checkbox" v-model="applicationData.visaFeeAcceptance" />
          <span
            >I am aware that the visa fee is not refunded if the visa is
            refused.</span
          >
        </div>

        <div class="w-full flex-col">
          <input type="checkbox" v-model="applicationData.insuranceAccepance" />
          <span
            >Applicable in case a multiple-entry visa is applied for (cf. field
            no 24): I am aware of the need to have an adequate travel medical
            insurance for my first stay and any subsequent visits to the
            territory of Member States.</span
          >
        </div>

        <div class="w-full flex-col">
          <input
            type="checkbox"
            v-model="applicationData.personalDataProcessingAcceptance"
          />
          <span
            >Applicable in case a multiple-entry visa is applied for (cf. field
            no 24): I am aware of the need to have an adequate travel medical
            insurance for my first stay and any subsequent visits to the
            territory of Member States. INFORMATION ON THE PROCESSING OF
            PERSONAL DATA The collection of the data required by this
            application form, the taking of your photograph and, if applicable,
            the taking of your fingerprints, are mandatory for the examination
            of the visa application; and any personal data concerning you which
            appear on the visa application form, as well as your fingerprints
            and your photograph will be supplied to the relevant authorities of
            the Member States and processed by those authorities, for the
            purposes of a decision on your visa application. Such data as well
            as data concerning the decision taken on your application or a
            decision whether to annul, revoke or extend a visa issued will be
            entered into, and stored, in the Visa Information System (VIS) for a
            maximum period of five years, during which it will be accessible to
            the visa authorities and the authorities competent for carrying out
            checks on visas at external borders and within the Member States,
            immigration and asylum authorities in the Member States for the
            purposes of verifying whether the conditions for the legal entry
            into, stay and residence on the territory of the Member States are
            fulfilled, of identifying persons who do not or who no longer fulfil
            these conditions, of examining an asylum application and of
            determining responsibility for such examination. Under certain
            conditions the data will be also available to designated authorities
            of the Member States (for Italy: the Ministry of Interior and the
            Police authority) and to Europol for the purpose of the prevention,
            detection and investigation of terrorist offences and of other
            serious criminal offences. The Ministry of Foreign Affairs and
            International Cooperation (Piazzale della Farnesina 1, 00135 Roma,
            www.esteri.it, dgit6@esteri.it) is the Italian authority responsible
            (controller) for processing the data. You have the right to obtain
            in any of the Member States communication of the data relating to
            you recorded in the VIS and of the Member State which transmitted
            the data, and to request that the data relating to you which are
            inaccurate be corrected, and that the data relating to you processed
            unlawfully be deleted. For information on the exercise of your right
            to check your personal data and have them corrected or deleted, as
            well as on legal remedies according to the national law of the State
            concerned, see www.esteri.it and www.vistoperitalia.esteri.it.
            Further information will be provided upon request by the authority
            examining your application. The Italian national supervisory
            competent authority on the protection of personal data is the
            Italian Authority for Data Protection (Piazza di Montecitorio 121,
            00186 Roma, www.garanteprivacy.it; tel.: +3906 696771).</span
          >
        </div>

        <div class="w-full flex-col">
          <input type="checkbox" v-model="applicationData.finalAcceptance" />
          <span
            >I declare that to the best of my knowledge all particulars supplied
            by me are correct and complete. I am aware that any false statements
            involve my application being rejected or to the annulment of a visa
            already granted and may result in prosecution under the law of the
            Member State that process the application. I undertake to leave the
            territory of the Member States before the expiry of the visa, if
            granted. I am aware that possession of a visa is only one of the
            prerequisites for entry into the European territory of the Member
            States. The mere granting of a visa does not entitle me to
            compensation if I fail to fulfil the conditions of Article 5 ,
            paragraph 1, of the Council Regulation n. 562/2006 (Schengen Borders
            Code) and I am thus refused entry. The prerequisites for entry will
            be checked again on entry into the European territory of the Member
            States.</span
          >
        </div>
      </div> -->

      <!-- <div class="flex w-full ">
        <div class="w-full flex flex-col">
          <div class="w-full">
            <label for="place">Place</label>
            <input
              class="w-full"
              type="input"
              name="place"
              v-model="applicationData.place"
            />
          </div>
          <div class="w-full">
            <label for="date">Date</label>
            <input
              class="w-full"
              type="date"
              name="date"
              v-model="applicationData.date"
            />
          </div>
        </div>
        <div class="w-full">
          <span
            >Signature (for minors, signature of parental authority/legal
            guardian):</span
          >
        </div>
      </div> -->

      <div class="flex">
        <div
          @click="onPrint"
          class="p-2 bg-red-200 flex flex-1 justify-center cursor-pointer hover:bg-red-300"
        >
          <span>Print</span>
        </div>
        <div
          @click="onReset"
          class="p-2 bg-yellow-200 flex flex-1 justify-center cursor-pointer hover:bg-yellow-300"
        >
          <span>Reset</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import html2pdf from "html2pdf.js";
// import printTemplate from "../templates/template.js";
import InputText from "@/components/InputText.vue";
import InputDate from "@/components/InputDate.vue";
import InputSelect from "@/components/InputSelect.vue";

export default {
  name: "MainView",
  components: { InputText, InputDate, InputSelect },
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
        sex: "",
        martialStatus: "",
        martialStatusOtherValue: "",
        minorsData: "",
        nationalIdentityNumber: "",
        travelDocumentType: "",
        travelDocumentTypeOtherValue: "",
        travelDocumentNumber: "",
        travelDocumentIssuedDate: "", // type date
        travelDocumentExpirationDate: "", // type date
        travelDocumentIssuedBy: "",
        address: "",
        email: "", // type email
        phone: "",
        otherResidence: "no",
        otherResidenceDocumentName: "",
        otherResidenceDocumentNumber: "",
        otherResidenceExpirationDate: "",
        isStudent: "no", // pivoting variable
        currentOccupation: "",
        employerFullName: "",
        employerAddress: "",
        employerPhone: "",
        educatinoalEstablishmentName: "",
        educatinoalEstablishmentAddress: "",
        travelPurpose: "",
        travelPurposeOtherValue: "",
        memberDestinationState: "",
        memberStateFirstEntry: "",
        entriesRequested: "",
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
        companyReference: {
          firstName: "",
          surname: "",
          address: "",
          phone: "",
          fax: "",
          email: "",
        },
        costsCoverage: {
          applicant: false,
          applicantTypes: {
            cash: false,
            check: false,
            creditCard: false,
            prepaidAccommodation: false,
            prepaidTransport: false,
            other: false,
            otherValue: "",
          },
          sponsor: false,
          referredPreviously: false,
          otherSponsors: false,
          otherSponsorsValue: "",
          sponsorTypes: {
            cash: false,
            accomodation: false,
            allCovered: false,
            prepaidTransport: false,
            other: false,
            otherValue: "",
          },
        },
        familyMember: {
          surname: "",
          firstName: "",
          dateOfBirth: "", // type date
          nationality: "",
          documentNumber: "",
        },
        relationshipType: {
          spouse: false,
          child: false,
          grandchild: false,
          dependent: false,
        },
        place: "", // *shared info in two sections
        date: "", // type date *shared info in two sections
        visaFeeAcceptance: false, // mandatory
        insuranceAccepance: false, // mandatory
        personalDataProcessingAcceptance: false, // mandatory
        finalAcceptance: false, // mandatory
      },
      sexOptions: [
        { name: "Male", value: "male" },
        { name: "Female", value: "female" },
      ],
      martialStatusOptions: [
        { name: "Single", value: "single" },
        { name: "Married", value: "married" },
        { name: "Separated", value: "separated" },
        { name: "Divorced", value: "divorced" },
        { name: "Widow(ed)", value: "widow(ed)" },
        { name: "Other", value: "other" },
      ],
      travelDocumentTypeOptions: [
        { name: "Ordinaty", value: "ordinary" },
        { name: "Diplomatic", value: "diplomatic" },
        { name: "Service", value: "service" },
        { name: "Official", value: "official" },
        { name: "Special", value: "special" },
        { name: "Other", value: "other" },
      ],
      yesNoOptions: [
        { name: "Yes", value: "yes" },
        { name: "No", value: "no" },
      ],
      travelPurposeOptions: [
        { name: "Tourism", value: "tourism" },
        { name: "Business", value: "business" },
        { name: "Visit", value: "visit" },
        { name: "Cultural", value: "cultural" },
        { name: "Sports", value: "sports" },
        { name: "Official", value: "official" },
        { name: "Medical", value: "medical" },
        { name: "Study", value: "study" },
        { name: "Transit", value: "transit" },
        { name: "Airport transit", value: "airportTransit" },
        { name: "Other", value: "other" },
      ],
      entriesOptions: [
        { name: "Single", value: "single" },
        { name: "Double", value: "double" },
        { name: "Multiple", value: "multiple" },
      ],
    };
  },
  mounted() {
    // console.log("mounted");
    // console.log(printTemplate);
    // console.log(printTemplate.replace("{{ title }}", "MISHA"));
    // this.loadTemplate();
  },
  computed: {
    isMartialStatusUnspecified() {
      let result = false;
      if (
        this.applicationData.martialStatus != "" &&
        this.applicationData.martialStatus === "other"
      ) {
        result = true;
      }
      return result;
    },

    isTravelDocumentTypeUnspecified() {
      let result = false;
      if (
        this.applicationData.travelDocumentType != "" &&
        this.applicationData.travelDocumentType === "other"
      ) {
        result = true;
      }
      return result;
    },
  },

  methods: {
    onPrint() {
      console.log("print requested");
      const element = this.$refs.target;
      const options = {
        margin: 1,
        filename: `${this.applicationData.firstName}-${this.applicationData.lastName}-application`,
        image: { type: "jpeg", quality: 0.98 },
        html2canvas: { scale: 2 },
        jsPDF: { unit: "in", format: "letter", orientation: "portrait" },
      };
      html2pdf().from(element).set(options).save();
    },
    onReset() {
      console.log("reset requested");
    },
    // async loadTemplate() {
    //   try {
    //     const response = await fetch("./templates/template.html"); // Adjust the path
    //     const text = await response.text();
    //     console.log("text loaded", text);
    //     // this.pdfContent = text.replace('{{ title }}', this.title); // Replace placeholders
    //   } catch (error) {
    //     console.error("Error loading template:", error);
    //   }
    // },
  },
};
</script>
