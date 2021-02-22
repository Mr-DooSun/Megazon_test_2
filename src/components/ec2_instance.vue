<template>
  <v-data-table
    :headers="headers"
    :items="aws_ec2"
    :items-per-page="5"
    class="elevation-1"
  ></v-data-table>
  
</template>

<script async='async'>
  import axios from 'axios';

  export default {
    data () {

      return {
        headers: [
          { text: 'VPC ID', value: 'vpc_id' },
          { text: 'Name', value: 'name' },
          { text: 'Instance ID', value: 'instance_id' },
          { text: 'Instance Type', value: 'instance_type' },
          { text: 'Private IP', value: 'private_ip' },
          { text: 'Private DNS Name', value: 'private_dns_name' },
          { text: 'Public IP', value : 'public_ip'},
          { text: 'Security Group', value : 'security_group'},
          { text: 'Instance State', value : 'instance_state'}
        ],

        aws_ec2: [],
      }
    },

    async mounted(){
      console.log('heheh')
      var ec2_instance_status = new Array();
      const instance_data_parsing = await axios.get('http://localhost:3000/instance_status')
      const instance_data_process = instance_data_parsing.data.Reservations
      
      for(var i=0; i<instance_data_process.length; i++) {
        ec2_instance_status[i]={
          vpc_id: instance_data_process[i]['Instances'][0]['VpcId'],
          name: instance_data_process[i]['Instances'][0]['Tags'][0]['Value'],
          instance_id: instance_data_process[i]['Instances'][0]['InstanceId'],
          instance_type: instance_data_process[i]['Instances'][0]['InstanceType'],
          private_ip: instance_data_process[i]['Instances'][0]['PrivateIpAddress'],
          private_dns_name: instance_data_process[i]['Instances'][0]['PrivateDnsName'],
          public_ip : instance_data_process[i]['Instances'][0]['PublicIpAddress'],
          security_group : instance_data_process[i]['Instances'][0]['SecurityGroups'][0]['GroupName'],
          instance_state : instance_data_process[i]['Instances'][0]['State']['Name'],
        }
      }
      console.log(ec2_instance_status)
      this.aws_ec2 = ec2_instance_status;
    },

  }
</script>