cmake_minimum_required(VERSION 3.16)
project(ShieldDegradationStudy)

#find Geant4
#The RREQUIRED keyword will cause CMAKe to fail if Geant4 is not found
#COMPONENTS lists the GEANT4 Libraries my aplication will use
#I am starting ith the basics, i will ad more  components like Geant4 analysis later on.

find_package(Geant4 REQUIRED COMPONENTS G4run G4event G4tracking G4digits_hits G4intercoms G4graphics_reps G4visualization)

include(${Geant4_USE_FILE}) #sets up compiler flags include directories etc

add_executable(
    ShieldDegradationStudy
    ShieldDegradationStudy.cc
    DetectorConstruction.cc
    PhysicsList.cc
    ActionInitialization.cc
    PrimaryGeneratorAction.cc
    # add other.cc files as i create them
)

target_link_libraries(ShieldDegradationStudy ${Geant4_LIBRARIES})