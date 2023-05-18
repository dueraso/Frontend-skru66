<template>
  <v-row justify="center" align="center">
    <v-col cols="12">
      <v-simple-table fixed-header height="300px">
        <template v-slot:default>
          <thead>
          <tr>
            <th class="text-left">Name</th>
            <th class="text-left">Calories</th>
            <th width="110">
              <v-btn outlined @click="openItem({})">
                <v-icon>mdi-plus</v-icon>
                เพิ่ม
              </v-btn>
            </th>
          </tr>
          </thead>
          <tbody>
          <tr v-for="(item, index) in desserts.data" :key="index">
            <td>{{ item.title }}</td>
            <td>{{ item.detail }}</td>
            <td>
              <v-btn fab small text @click="openItem(item)">
                <v-icon>mdi-pen</v-icon>
              </v-btn>
              <v-btn fab small text @click="onDelete(item)">
                <v-icon>mdi-delete-outline</v-icon>
              </v-btn>
            </td>
          </tr>
          </tbody>
        </template>
      </v-simple-table>

      <div class="text-center">
        <v-dialog
          v-model="dialog"
          width="500"
          persistent
        >
          <v-card>
            <v-card-title class="text-h5 grey lighten-2 mb-3">
              Privacy Policy
            </v-card-title>

            <v-card-text>
              <v-text-field
                v-model="item.title"
                label="title"
                outlined
                clearable
                dense
              ></v-text-field>
              <v-text-field
                v-model="item.detail"
                label="detail"
                outlined
                clearable
                dense
              ></v-text-field>
            </v-card-text>

            <v-divider></v-divider>

            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn
                color="primary"
                text
                @click="confirm"
              >
                ok
              </v-btn>
              <v-btn
              color="primary"
              text
              @click="dialog = false"
            >
              cancel
            </v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>
      </div>
    </v-col>
  </v-row>
</template>

<script src="./index.js"/>
