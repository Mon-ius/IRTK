SET(CONTRIB_INCLUDES
    ../include/*.h
)

SET(CONTRIB_SRCS 
    irtkArith.cc
    irtkCityBlockDistanceTransform.cc
    irtkEigenAnalysis.cc
    irtkEuclideanDistanceTransform.cc
    irtkManifoldLearning.cc
    irtkMatrix3x3.cc
    irtkPairwiseSimilarity.cc
    irtkSpectralClustering.cc
    irtkVector3.cc
)

ADD_LIBRARY(contrib++ ${CONTRIB_INCLUDES} ${CONTRIB_SRCS})
INSTALL_FILES(/include FILES ${CONTRIB_INCLUDES})
