<script setup>
import aviato from '@images/logos/aviato.png'
import bitbank from '@images/logos/bitbank.png'
import zipcar from '@images/logos/zipcar.png'

const earnings = [
  {
    avatar: zipcar,
    title: '固定薪资',
    subtitle: '薪资',
    amount: '¥1,245,800',
    progress: 'primary',
  },
  {
    avatar: bitbank,
    title: '投资收入',
    subtitle: '股票 & 基金收益',
    amount: '¥896,500',
    progress: 'info',
  },
  {
    avatar: aviato,
    title: '技术服务',
    subtitle: '软件授权 & 云服务',
    amount: '¥2,112,300',
    progress: 'secondary',
  },
]
</script>

<template>
  <VCard>
    <VCardItem>
      <VCardTitle>年度总收入</VCardTitle>

      <template #append>
        <div class="me-n3">
          <MoreBtn />
        </div>
      </template>
    </VCardItem>

    <VCardText>
      <div class="d-flex align-center">
        <h3 class="text-h3">
          ¥4,254,600
        </h3>
        <VIcon
          size="24"
          icon="ri-arrow-up-s-line"
          color="success"
        />
        <div class="text-success">
          15%
        </div>
      </div>
      <div class="text-body-1 mb-12">
        与去年3,698,200元相比
      </div>

      <VList class="card-list">
        <VListItem
          v-for="earning in earnings"
          :key="earning.title"
        >
          <template #prepend>
            <VAvatar
              rounded
              :image="earning.avatar"
              variant="tonal"
            />
          </template>

          <VListItemTitle class="font-weight-medium">
            {{ earning.title }}
          </VListItemTitle>
          <VListItemSubtitle class="text-body-1">
            {{ earning.subtitle }}
          </VListItemSubtitle>

          <template #append>
            <div>
              <h6 class="text-h6 mb-2">
                {{ earning.amount }}
              </h6>
              <VProgressLinear
                :color="earning.progress"
                model-value="80"
                rounded-bar
                rounded
              />
            </div>
          </template>
        </VListItem>
      </VList>
    </VCardText>
  </VCard>
</template>

<style lang="scss" scoped>
.card-list {
  --v-card-list-gap: 1.5rem;
}
</style>
