const Discord = require("discord.js");
const colors = require("colors");
const db = require('quick.db')
const fs = require('fs');
const request = require('request');
const client = new Discord.Client({
    //fetchAllMembers: false,
    //restTimeOffset: 0,
    //restWsBridgetimeout: 100,
    shards: "auto",
    allowedMentions: {
        parse: [],
        repliedUser: false,
    },
    partials: ['MESSAGE', 'CHANNEL', 'REACTION'],
    intents: [
        Discord.Intents.FLAGS.GUILDS,
        Discord.Intents.FLAGS.GUILD_MEMBERS,
        //Discord.Intents.FLAGS.GUILD_BANS,
        //Discord.Intents.FLAGS.GUILD_EMOJIS_AND_STICKERS,
        //Discord.Intents.FLAGS.GUILD_INTEGRATIONS,
        //Discord.Intents.FLAGS.GUILD_WEBHOOKS,
        //Discord.Intents.FLAGS.GUILD_INVITES,
        Discord.Intents.FLAGS.GUILD_VOICE_STATES,
        //Discord.Intents.FLAGS.GUILD_PRESENCES,
        Discord.Intents.FLAGS.GUILD_MESSAGES,
        Discord.Intents.FLAGS.GUILD_MESSAGE_REACTIONS,
        //Discord.Intents.FLAGS.GUILD_MESSAGE_TYPING,
        //Discord.Intents.FLAGS.DIRECT_MESSAGES,
        //Discord.Intents.FLAGS.DIRECT_MESSAGE_REACTIONS,
        //Discord.Intents.FLAGS.DIRECT_MESSAGE_TYPING
    ],
    presence: {
        activity: {
            name: `Music`,
            type: "LISTENING",
        },
        status: "online"
    }
});

client.on('ready', client => {
console.log(`bot funfando <3 newba gostosão`)
})


client.on("guildMemberAdd", async (member) => {

    //definindo servidor
    let guild = client.guilds.cache.get ("1003364122278252554");
    // definindo canal 
    let channel = client.channels.cache.get("1003413590860103680");
    //var emoj
    let emoji = member.guild.emojis.cache.find(emoji => emoji.name === ''); //pesquisando emoji por nome 

    if(guild != member.guild) {
        return console.log('Sai daki, você não é do meu serv')
    } else {
        let embed = new Discord.MessageEmbed()
        
        .setColor('#f93e54') // setando cor da mensagem
        .setAuthor(member.user.tag, member.user.displayAvatarURL()) // puxando a tag e icone do usuário
        .setTitle(`Boas-vindas`) // setando titulo
        .setImage('https://user-images.githubusercontent.com/22198380/138895788-bcd19a6e-026f-410c-b14e-1d35990e7ad0.gif') //puxando imagem ou gif 
        .setDescription(`${member.user}, Boas-vindas ao servidor ${guild.name}! Atualmente estamos com ${member.guild.memberCount} membros. `) // descrição da mensagem
        .addField('Canais', 'Siga as regras do servidor <#1003375397192335472> ') //mencionar canais do discord
        .setThumbnail(member.user.displayAvatarURL({ dynamic: true, format: "png", size: 1024})) //destacar foto do avatar do membro novo
        .setFooter('ID do usuário:' + member.user.id) // id do usuário no rodapé
        .setTimestamp(); // hora que usuário entrou no discord

        channel.send({ embeds:[embed] })

    }
})


process.on('unhandledRejection', (reason, p) => {
    console.log(' [antiCrash] :: Unhandled Rejection/Catch');
    console.log(reason, p);
});
process.on("uncaughtException", (err, origin) => {
    console.log(' [antiCrash] :: Uncaught Exception/Catch');
    console.log(err, origin);
})
process.on('uncaughtExceptionMonitor', (err, origin) => {
    console.log(' [antiCrash] :: Uncaught Exception/Catch (MONITOR)');
    console.log(err, origin);
});
process.on('multipleResolves', (type, promise, reason) => {
    console.log(' [antiCrash] :: Multiple Resolves');
    console.log(type, promise, reason);
});


client.login(fs.readFileSync('./token.txt').toString())

