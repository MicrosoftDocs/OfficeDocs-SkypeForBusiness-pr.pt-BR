---
title: Autenticação de usuário e cliente para o Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Um usuário confiável é aquele cujas credenciais foram autenticadas por um servidor confiável no Skype para Business Server 2015. Esse servidor é geralmente um servidor Standard Edition, servidor de Front End Enterprise Edition ou diretor. Skype para Business Server depende do Active Directory Domain Services como o repositório de back-end único e confiável de credenciais de usuário.
ms.openlocfilehash: d8fa9265a4c27432dd4c2dba6e15c07e39f348b8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="user-and-client-authentication-for-skype-for-business-server-2015"></a>Autenticação de usuário e cliente para o Skype for Business Server 2015
 
Um usuário confiável é aquele cujas credenciais foram autenticadas por um servidor confiável no Skype para Business Server 2015. Esse servidor é geralmente um servidor Standard Edition, servidor de Front End Enterprise Edition ou diretor. Skype para Business Server depende do Active Directory Domain Services como o repositório de back-end único e confiável de credenciais de usuário.
  
Autenticação é o provisionamento de credenciais de usuário em um servidor confiável. Skype para Business Server usa os seguintes protocolos de autenticação, dependendo do status e o local do usuário.
  
- **Protocolo do MIT Kerberos versão 5 de segurança** para usuários internos com credenciais do Active Directory. Kerberos requer conectividade de cliente com o Active Directory Domain Services, o motivo pelo qual ele não pode ser usado para autenticar clientes fora do firewall corporativo.
    
- **Protocolo NTLM** para usuários com credenciais do Active Directory que estão se conectando de um ponto de extremidade fora do firewall corporativo. O serviço de borda de acesso passa as solicitações de logon para um diretor, se presente, ou um servidor Front-End para autenticação. O próprio serviço de borda de acesso não executa nenhuma autenticação.
    
    > [!NOTE]
    > O protocolo NTLM oferece proteção contra ataques mais fraca que o Kerberos; assim, algumas organizações minimizam o uso de NTLM. Como resultado, o acesso ao Skype para Business Server 2015 pode ser restrito para interno ou clientes conectados por meio de uma conexão VPN ou DirectAccess. 
  
- **Protocolo Digest** para os chamados usuários anônimos. Usuários anônimos são usuários externos que não possuem credenciais reconhecidas do Active Directory, mas que foram convidados para uma conferência no local e possuem uma chave de conferência válida. A autenticação Digest não é usada para nenhuma outra interação do cliente.
    
Skype para autenticação de negócios Server 2015 consiste em duas fases:
  
1. Uma associação de segurança é estabelecida entre o cliente e o servidor.
    
2. O cliente e o servidor usam a associação de segurança existente para assinar mensagens enviadas e para verificar as mensagens recebidas. Mensagens não autenticadas de um cliente não são aceitas quando uma autenticação está habilitada no servidor.
    
Uma marca da confiança do usuário é anexada a cada mensagem originária de um usuário, não à identidade do usuário em si. O servidor verifica se há credenciais de usuário válidas em cada mensagem. Se as credenciais de usuário forem válidas, a mensagem não será contestada nem pelo primeiro servidor, nem pelos outros servidores da nuvem de servidores confiáveis.
  
Usuários com credenciais válidas emitidas por um parceiro federado são confiáveis, porém são opcionalmente impedidos por restrições adicionais de aproveitar toda a gama de privilégios concedidos aos usuários internos.
  
Os protocolos ICE e TURN também utilizam o mecanismo de desafio Digest, conforme descrito no IETF TURN RFC.
  
Certificados de cliente fornecem uma maneira alternativa dos usuários serem autenticados pelo Skype para Business Server 2015. Em vez de fornecer um nome de usuário e senha, os usuários possuem um certificado e a chave privada correspondente ao certificado exigida para resolver um desafio criptográfico. (Esse certificado deve ter um nome de entidade ou nome alternativo da entidade que identifica o usuário e deve ser emitido por uma autoridade de certificação raiz confiável para servidores que executam o Skype para Business Server 2015, estar dentro do período de validade do certificado e não foi revogado.) Para ser autenticado, os usuários precisam apenas digitar um número de identificação pessoal (PIN). Os certificados são particularmente úteis para telefones, celulares e outros dispositivos onde é difícil inserir um nome de usuário e senha.
  

