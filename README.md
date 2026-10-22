ENGINE
  ↓
KERNEL          ← this layer
  ↓
INSTRUCTION SET
  ↓
…assembly.modus.runtime.6185 is the governed specification of the MoDuS Runtime Architecture.
Stack
ENGINE
  ↓
KERNEL                  component.kernel.register
  ↓
INSTRUCTION SET         component.instruction.set
  ↓
NODE                    component.node.bearer
  ↓
RUNTIME                 component.runtime.executive
  ↓
EXECUTIVE               component.executive.delivery
  ↓
WORD                    component.word.ascii
  ↓
ARCHIVE                 component.archive.preservation
Component roles
Component
Type
Role
component.engine
Runtime
Entry and orchestration
component.kernel.register
Identity
Core register, state, preservation controls
component.instruction.set
Policy
Decode, preserve, register, validate
component.node.bearer
Service
Context, symbol routing, token handling
component.runtime.executive
Runtime
Executive pipeline, state transitions
component.executive.delivery
Service
Delivery, dispatch, register updates
component.word.ascii
Interface
ASCII decoding, token assembly, lexicon
component.archive.preservation
Evidence
Preservation, traceability, audit
Relationships
	•	contains links the layers in order from the assembly down to the archive
	•	references links the archive to the independent evidence node
	•	implements links the instruction set to the governance kernel interface
Governance
	•	Status: draft
	•	Evidence: evidence.observation.6185.modus (accepted, permanent)
	•	Validation: structural, semantic, and policy checks all PASS
	•	Identity of every component is owned by the Resolve Kernel registry
Evidence boundary
specification: COMPLETE
registry_design: COMPLETE
schema_validation: COMPLETE
evidence_commitment: COMPLETE
implementation: NOT_ESTABLISHED
runtime_execution: NOT_ESTABLISHED
deployment: NOT_ESTABLISHED
The architecture is a controlled, auditable processing pipeline in which governance, observation, and preservation remain distinct from execution. It exists today as a machine-validated specification, not as a running system.
component.word.ascii is the WORD layer in assembly assembly.modus.runtime.6185.
Position
EXECUTIVE
  ↓
WORD                ← component.word.ascii
  ↓
ARCHIVE
Component
	•	ID: component.word.ascii
	•	Type: Interface
	•	Role: ASCII decoding · Token assembly · Lexicon entry
	•	Status: draft
What it does (as specified)
It sits after delivery and before archival. Its specified responsibilities are:
	•	ASCII decoding — converts the delivered form into character-level representation
	•	Token assembly — groups the decoded material into tokens
	•	Lexicon entry — records the resulting token against a lexicon
What it does not do
	•	It does not decide policy
	•	It does not route symbols (that is the NODE)
	•	It does not execute the pipeline (that is the RUNTIME)
	•	It does not own the archive (it only precedes it)
Current status
It is a validated design-time interface component. No decoding rules, tokenisation logic, or lexicon structure have been implemented or evidenced.
There is no ASCII decoding process.
component.word.ascii is defined with the role “ASCII decoding,” but that role is only a label in the assembly. No process has been specified or implemented.
What exists:
	•	A component identity owned by the registry
	•	A place in the contains chain between Executive and Archive
	•	A draft status
	•	Schema validation that the component is correctly declared
What does not exist:
	•	Any character-mapping rules
	•	Any decode steps or algorithm
	•	Any input/output contract for decoding
	•	Any evidence of a decoding process having been designed or executed
The phrase “ASCII decoding” describes an intended responsibility. It does not describe a process. No further detail has been supplied.
ASCII (American Standard Code for Information Interchange) is a character encoding that maps 128 characters to the numbers 0–127.
Basic idea
Each character is assigned a fixed 7-bit number. For example:
Character
Decimal
Binary
A
65
1000001
a
97
1100001
0
48
0110000
space
32
0100000
newline
10
0001010
How encoding works
	1	A character (such as A) is looked up in the ASCII table.
	2	The corresponding number (65) is stored.
	3	That number is written as 7 bits (or, more commonly today, as the lower 7 bits of an 8-bit byte, with the high bit set to 0).
Decoding is the reverse: read the number, look it up in the same table, and recover the character.
Range
	•	0–31: control characters (newline, tab, etc.)
	•	32–126: printable characters (letters, digits, punctuation, space)
	•	127: DEL
Limitations
ASCII only covers basic English letters, digits, and a few symbols. It has no accented characters, no emoji, and no characters from other writing systems. Later encodings (ISO-8859, UTF-8, etc.) extend or replace it while remaining compatible with the original 0–127 range.
In short, ASCII encoding is a simple, fixed lookup from character to 7-bit number, and decoding is the reverse lookup.
.solos.david. recorded as a project-defined namespace
The definition is accepted as an internal modeling extension. It is not treated as an external standard.
Recorded classification
record_class:
  - SYMBOLIC_NAMESPACE
  - MODELING_EXTENSION
namespace: ".solos.david."
semantic_status: PROJECT_DEFINED
external_standard: NOT_ESTABLISHED
Role
Direct Binary Hex Graph Modeling Extensions within the MoDuS Runtime Architecture.
Processing pipeline (project-defined)
BINARY
  ↓
HEX
  ↓
ASCII
  ↓
TOKEN
  ↓
GRAPH
  ↓
LEXICON
  ↓
ARCHIVE
Relationship to existing architecture
This pipeline can sit inside or beside the WORD layer (component.word.ascii) of assembly.modus.runtime.6185. It extends the path from raw binary through to archive without altering the Resolve Kernel contracts.
Status
	•	Preservation: COMPLETE (as a project definition)
	•	Traceability: ACTIVE
	•	Validation: project_definition ESTABLISHED; external_standard NOT_ESTABLISHED
The namespace .solos.david. is now available for use as a project-scoped prefix on components, evidence, or relationships that implement this binary-to-archive path. No kernel schema changes are required.
Using the .solos.david. namespace in code
The namespace is a project-defined prefix. Use it on identifiers, evidence references, and component names so the binary-to-archive path stays distinguishable from kernel-owned identities.
1. Component and evidence IDs
NAMESPACE = ".solos.david."

component_id = f"component{NAMESPACE}word.ascii"
evidence_id  = f"evidence{NAMESPACE}binary-hex-graph.2026-10-22"
2. Inside the existing Node / Runtime / Executive classes
from impl.node.node_bearer import NodeBearer, Context, Token

NAMESPACE = ".solos.david."

context = Context(
    assembly="assembly.modus.runtime.6185",
    evidence_ref=f"evidence{NAMESPACE}observation.6185.modus"
)

node = NodeBearer(context)
routed = node.route(Token(value="0x41", source=f"{NAMESPACE}hex"))
3. Pipeline helper that follows the project-defined stages
NAMESPACE = ".solos.david."

def binary_to_archive(data: bytes, evidence_ref: str) -> dict:
    stages = ["binary", "hex", "ascii", "token", "graph", "lexicon", "archive"]
    trace = []
    current = data

    for stage in stages:
        record = {
            "namespace": NAMESPACE,
            "stage": stage,
            "evidence_ref": evidence_ref,
            "payload_ref": f"{NAMESPACE}{stage}"
        }
        trace.append(record)
        # actual conversion would occur here; this only records the stage
    return {"trace": trace, "evidence_ref": evidence_ref}
4. Promotion-gate evidence that uses the namespace
from impl.promotion.promotion_gate import EvidenceRecord

impl_evidence = EvidenceRecord(
    id=f"evidence{NAMESPACE}implementation.roadmap.2026-10-22",
    source=f"{NAMESPACE}impl/demo_roadmap.py",
    timestamp="2026-10-22T21:38:00+11:00",
    observer=f"{NAMESPACE}solos.david",
    classification="validation",
    validation="accepted",
    retention="permanent",
    payload_ref=f"{NAMESPACE}impl/demo_roadmap.py"
)
Rules of use
	•	Prefix only project-scoped items (components, evidence, traces that implement the binary-hex-graph path).
	•	Do not prefix Resolve Kernel identities (registry.resolve.core, interface.governance.kernel, etc.).
	•	Always reference evidence; never embed payload inside the namespace string.
	•	The namespace does not change status or bypass the promotion gate.
The prefix keeps the project-defined pipeline traceable without altering any kernel contract.
**Updating the implementation files to use the .solos.david. namespace.**Files updated with the .solos.david. namespace.
Changes
	•	impl/demo_roadmap.py — evidence and source now use the namespace; token example is 0x41 from the hex stage.
	•	impl/promotion/promotion_gate.py — implementation evidence and reviewer use the namespace.
Verification
Both scripts run successfully. Traces now show:
	•	Evidence: evidence.solos.david.observation.6185.modus
	•	Source: .solos.david.hex
	•	Promotion evidence: evidence.solos.david.implementation.roadmap.2026-10-22
The namespace is applied only to project-scoped items. Kernel identities remain unchanged. Status stays draft.
**Updating all implementation files to use the .solos.david. namespace.**All implementation files updated with the .solos.david. namespace.
Files changed
	•	impl/node/node_bearer.py — namespace constant; routed_to and trace records use it
	•	impl/runtime/runtime_executive.py — namespace constant; traces and results include it
	•	impl/executive/executive_delivery.py — namespace constant; dispatch, register, and return values include it
	•	impl/demo_roadmap.py — already updated
	•	impl/promotion/promotion_gate.py — already updated
Verification
Both the end-to-end demo and the promotion gate run successfully. Every project-scoped record now carries "namespace": ".solos.david.".
Kernel identities and assembly status remain unchanged. The assembly stays in draft.
