<template><div id="app"><v-app><v-content>
			<v-container class="mt-5" grid-list-md text-xs-center>
        <v-layout row wrap>
          <v-flex xs10 offset-xs1>
			 <v-form v-on:submit.prevent="addNote">
				<v-text-field v-model="input" solo placeholder="" no-resize hide-details color="primary"></v-text-field>
				<v-btn @click="addNote" v-bind:disabled="!hasInputText" outline color="primary">add</v-btn>
       </v-form>
        <v-data-table :items="notes" hide-actions hide-headers class="elevation-1">
          <template slot="items" slot-scope="props">
            <td>
              <v-layout row wrap>
                <v-flex xs11>
                  <v-card-text>{{ props.item.name }}</v-card-text>
                </v-flex>
                <v-flex xs1>
                    <v-btn icon @click="deleteNote(props.index)">
                      <v-icon outline color="red">delete</v-icon>
                    </v-btn>
                </v-flex>
              </v-layout>
            </td>
          </template>
          <template slot="no-data">
            <v-card-text>There are no todos left</v-card-text>
          </template>
        </v-data-table>
          </v-flex>
        </v-layout>
			</v-container>
		</v-content></v-app></div></template>
