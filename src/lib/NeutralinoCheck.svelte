<script lang="ts">
    import {computer} from '@neutralinojs/lib';
    let osInfo = computer.getOSInfo();
</script>

<p>
    {#await osInfo}
        Sending a Neutralino request…
    {:then result}
        Your operating system is {result.name} {result.version} ({result.description})
    {:catch error}
        Could not get operating system information: {error.message}
    {/await}
</p>