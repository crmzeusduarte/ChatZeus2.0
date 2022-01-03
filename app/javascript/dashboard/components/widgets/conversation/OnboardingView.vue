<template>
  <div class="columns onboarding-wrap">
	<div class="onboarding">
      	    <div class="scroll-wrap">
		<div class="features-item">
			<img src="~dashboard/assets/images/chatzeus.svg" alt="Logo ChatZeus">
		</div>
		<div class="features-item">
			<img src="~dashboard/assets/images/dashboard.png" height="80%" alt="ChaZeus">
		</div>
	    </div>
	</div>		
  </div>
</template>
<script>
import { mapGetters } from 'vuex';
import accountMixin from '../../../mixins/account';

export default {
  mixins: [accountMixin],
  computed: {
    ...mapGetters({ globalConfig: 'globalConfig/get' }),
    newInboxURL() {
      return this.addAccountScoping('settings/inboxes/new');
    },
    newAgentURL() {
      return this.addAccountScoping('settings/agents/list');
    },
    newLabelsURL() {
      return this.addAccountScoping('settings/labels/list');
    },
  },
};
</script>
<style lang="scss" scoped>
.onboarding-wrap {
  display: flex;
  font-size: var(--font-size-small);
  justify-content: center;
  overflow: auto;
  text-align: left;
}
.onboarding {
  height: 100vh;
  overflow: auto;
}

.scroll-wrap {
  padding: var(--space-larger) 13.6rem;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.features-item {
  margin-bottom: var(--space-large);
}

.conversation--title {
  margin-left: var(--space-minus-smaller);
}

.page-title {
  font-size: var(--font-size-big);
  font-weight: var(--font-weight-bold);
  margin-bottom: var(--space-one);
}

.block-title {
  font-weight: var(--font-weight-bold);
  margin-bottom: var(--space-smaller);
  margin-left: var(--space-minus-large);
}

.intro-body {
  margin-bottom: var(--space-small);
  line-height: 1.5;
}

.onboarding--link {
  color: var(--w-500);
  font-weight: var(--font-weight-medium);
  text-decoration: underline;
}

.emoji {
  width: var(--space-large);
  display: inline-block;
}
</style>
