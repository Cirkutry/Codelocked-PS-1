<script lang="ts">
  import * as Tabs from "$lib/components/ui/tabs";
  import * as Table from "$lib/components/ui/table/index.js";

  const crewLogs = {
    active: [
      { name: "Cmdr. Aria Kovács", log: "Inspecting pressure seals on Habitat Dome C after minor fluctuation alert." },
      { name: "Dr. Mateo Ishida", log: "Conducting microbial analysis on Martian regolith samples." },
      { name: "Eng. Lila Sørensen", log: "Adjusting reactor coolant flow rates to stabilize core temperature." },
      { name: "Spec. Rohan Patel", log: "Calibrating drone mapping sensors for next surface survey." }
    ],
    rest: [
      { name: "Lt. Sofia Chen", log: "In rest quarters following completion of rover terrain diagnostics." },
      { name: "Dr. Rafael Mendes", log: "Reviewing patient biosigns during scheduled off-duty period." },
      { name: "Tech. Helena Volkova", log: "Standby mode, awaiting part delivery for hydro system repairs." },
      { name: "Pilot Owen Grant", log: "Resting after completing supply shuttle docking procedures." }
    ]
  };
</script>

<section id="log" class="container mx-auto px-6">
	<div class="max-w-7xl mx-auto flex flex-col py-12 gap-8 w-full">
    <h2 class="text-4xl font-extrabold mb-8">Crew Operational Log</h2>

    <Tabs.Root value="active">
      <Tabs.List>
        <Tabs.Trigger value="active" class="px-4 py-2 font-medium data-[state=active]:border-b-2 data-[state=active]:border-primary data-[state=active]:text-primary">
          Active Missions
        </Tabs.Trigger>
        <Tabs.Trigger value="rest" class="px-4 py-2 font-medium data-[state=active]:border-b-2 data-[state=active]:border-primary data-[state=active]:text-primary">
          Rest / Standby
        </Tabs.Trigger>
      </Tabs.List>

      <Tabs.Content value="active">
        <Table.Root>
          <Table.Caption>Currently active crew logs.</Table.Caption>
          <Table.Header>
            <Table.Row>
              <Table.Head>Name</Table.Head>
              <Table.Head>Log Entry</Table.Head>
            </Table.Row>
          </Table.Header>
          <Table.Body>
            {#each crewLogs.active as entry}
              <Table.Row>
                <Table.Cell class="font-medium">{entry.name}</Table.Cell>
                <Table.Cell>{entry.log}</Table.Cell>
              </Table.Row>
            {/each}
          </Table.Body>
        </Table.Root>
      </Tabs.Content>

      <Tabs.Content value="rest">
        <Table.Root>
          <Table.Caption>Crew logs during rest/standby.</Table.Caption>
          <Table.Header>
            <Table.Row>
              <Table.Head>Name</Table.Head>
              <Table.Head>Log Entry</Table.Head>
            </Table.Row>
          </Table.Header>
          <Table.Body>
            {#each crewLogs.rest as entry}
              <Table.Row>
                <Table.Cell class="font-medium">{entry.name}</Table.Cell>
                <Table.Cell>{entry.log}</Table.Cell>
              </Table.Row>
            {/each}
          </Table.Body>
        </Table.Root>
      </Tabs.Content>
    </Tabs.Root>
  </div>
</section>
