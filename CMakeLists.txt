CMAKE_MINIMUM_REQUIRED(VERSION 2.8)

SET(QHP_FILE "doc.qhp")
SET(QHCP_FILE "mtrack-collection.qhcp")
SET(QHC_FILE "mtrack-collection.qhc")

SET(HTML_FILES "index.html"
	"new_inventory.html"
	"new_medication.html"
	"new_patient.html"
	"new_pharmacist.html"
	"new_prescriber.html"
	"new_prescription.html"
	"printing_labels.html"
	"search_formulary.html"
	"search_inventory.html"
	"search_patients.html"
	"search_pharmacists.html"
	"search_prescribers.html"
	"search_prescriptions.html"
	"toggle_active.html"
	"write_off_inventory.html"
)

ADD_CUSTOM_TARGET(documentation ALL
	COMMAND qcollectiongenerator ${PROJECT_SOURCE_DIR}/doc/${QHCP_FILE} -o ${CMAKE_BINARY_DIR}/${EXE_DIR}/${QHC_FILE}
)

ADD_CUSTOM_TARGET(doc_files true SOURCES ${HTML_FILES} ${QHP_FILE} ${QHCP_FILE})
