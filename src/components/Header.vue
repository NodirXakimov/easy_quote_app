<template>
    <div class="row justify-content-center my-4">
        <div class="col-8">
            <div class="progress" style="height: 20px;">
                <div class="progress-bar" role="progressbar" :style="{width: (quotesCount/maxQuote) * 100 + '%'}" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">
                    {{ quotesCount }} / {{ maxQuote }}
                </div>
            </div>
        </div>
        {{ quotesCount }} / {{ maxQuote }}
    </div>
</template>
<script>
export default {
    props: ['maxQuote', 'quotesCount']
}
</script>