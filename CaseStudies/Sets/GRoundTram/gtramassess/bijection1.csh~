#!/bin/csh -fx

set KM3_SRC    = bijection1_src.km3
set KM3_TGT    = bijection1_tgt.km3
set KM3_SRC_PKG = Person
set KM3_TGT_PKG = Employee

set FWD_UNCAL  = "fwd_uncal -ge -sb -cl -zn -fi -np -sa -t -rw -as "
# inplace
set BWD_UNCAL  = "bwd_uncal -cm"
set UNQL_TRANS = bijection1.unql
set DOTTY      = "~/programs/bdotty/bdotty"



# T1 -----------------------------------------------------------------------------------

set DOT_SRC    = bijection1_2_src.dot
set DOT_TGT    = bijection1_2_tgt.dot
set XG         = ${DOT_TGT:r}.xg
set EI         = ${DOT_TGT:r}.ei
set DOT_TGT_UPD = ${DOT_TGT:r}_upd.dot
set DOT_SRC_UPD = ${DOT_SRC:r}_upd.dot



dot -Tpng ${DOT_SRC} > ${DOT_SRC:r}.png

# ~/proj/big/git/BiG/src/unqlplus -db ${DOT_SRC} -q ${UNQL_TRANS} -dot ${DOT_TGT} \
# -iv ${KM3_SRC} -ip ${KM3_SRC_PKG} \
# -ov ${KM3_TGT} -op ${KM3_TGT_PKG}

# fwd trans.
${FWD_UNCAL} -db ${DOT_SRC} -uq ${UNQL_TRANS} -dot ${DOT_TGT} -png ${DOT_TGT:r}.png -xg ${XG} -ei ${EI}

cp ${DOT_TGT} ${DOT_TGT_UPD}

${DOTTY}  ${DOT_TGT_UPD}

dot -Tpng ${DOT_TGT_UPD} > ${DOT_TGT:r}_upd.png

# bwd trans.
${BWD_UNCAL} -db ${DOT_SRC} -dot ${DOT_TGT_UPD} -udot ${DOT_SRC_UPD} -png ${DOT_SRC:r}_upd.png -xg ${XG} -ei ${EI} 

display ${DOT_SRC:r}_upd.png



# T4 -----------------------------------------------------------------------------------

set DOT_SRC    = bijection1_4_src.dot
set DOT_TGT    = bijection1_4_tgt.dot
set XG         = ${DOT_TGT:r}.xg
set EI         = ${DOT_TGT:r}.ei
set DOT_TGT_UPD = ${DOT_TGT:r}_upd.dot
set DOT_SRC_UPD = ${DOT_SRC:r}_upd.dot

dot -Tpng ${DOT_SRC} > ${DOT_SRC:r}.png

# fwd trans.
${FWD_UNCAL} -db ${DOT_SRC} -uq ${UNQL_TRANS} -dot ${DOT_TGT} -png ${DOT_TGT:r}.png -xg ${XG} -ei ${EI}

cp ${DOT_TGT} ${DOT_TGT_UPD}

${DOTTY}  ${DOT_TGT_UPD}

dot -Tpng ${DOT_TGT_UPD} > ${DOT_TGT:r}_upd.png

# bwd trans.
${BWD_UNCAL} -db ${DOT_SRC} -dot ${DOT_TGT_UPD} -udot ${DOT_SRC_UPD} -png ${DOT_SRC:r}_upd.png -xg ${XG} -ei ${EI} 

display ${DOT_SRC:r}_upd.png

