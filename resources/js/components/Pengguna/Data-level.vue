<template>
    <div class="container">
        <div class="row justify-content-center mt-5">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Data Level</div>

                    <div class="card-body">
                        <div class="form-group">
                            <div class="table-responsive">
                                <table class="table">
                                    <thead>
                                        <tr>
                                            <th>Nama Level</th>
                                            <th>Aksi</th>
                                        </tr>
                                    </thead>
                                    <tbody>
                                        <tr v-for="level in levels" :key="level.message">
                                            <td>{{ level.nama_level }}</td>
                                            <td> Edit | Hapus </td>
                                        </tr>
                                    </tbody>
                                </table>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            levels: {}
        }
    },
    methods: {
        loadData() {
            axios.get('api/ambildatalevel').then(({ data }) => (this.levels = data))
        }
    },
    created() {
        this.loadData();
    }
}
</script>
