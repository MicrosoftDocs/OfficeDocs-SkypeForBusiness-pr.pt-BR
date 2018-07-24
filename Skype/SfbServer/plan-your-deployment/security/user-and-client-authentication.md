---
title: Autenticação de cliente e usuário para Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Um usuário confiável é aquele cujas credenciais foram autenticadas por um servidor confiável no Skype para Business Server. Esse servidor é geralmente um servidor Standard Edition, servidor de Front End Enterprise Edition ou diretor. Skype para Business Server depende do Active Directory Domain Services como o repositório de back-end único e confiável de credenciais de usuário.
ms.openlocfilehash: c16e70641d2ce6e25b932904e9371f7ddf03bdd8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21010643"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Autenticação de cliente e usuário para Skype para Business Server
 
Um usuário confiável é aquele cujas credenciais foram autenticadas por um servidor confiável no Skype para Business Server. Esse servidor é geralmente um servidor Standard Edition, servidor de Front End Enterprise Edition ou diretor. Skype para Business Server depende do Active Directory Domain Services como o repositório de back-end único e confiável de credenciais de usuário.
  
Autenticação é o provisionamento de credenciais de usuário em um servidor confiável. Skype para Business Server usa os seguintes protocolos de autenticação, dependendo do status e o local do usuário.
  
- **Protocolo do MIT Kerberos versão 5 de segurança** para usuários internos com credenciais do Active Directory. Kerberos requer conectividade de cliente com o Active Directory Domain Services, o motivo pelo qual ele não pode ser usado para autenticar clientes fora do firewall corporativo.
    
- **Protocolo NTLM** para usuários com credenciais do Active Directory que estão se conectando de um ponto de extremidade fora do firewall corporativo. O serviço de borda de acesso passa as solicitações de logon para um diretor, se presente, ou um servidor Front-End para autenticação. O próprio serviço de borda de acesso não executa nenhuma autenticação.
    
    > [!NOTE]
    > O protocolo NTLM oferece proteção contra ataques mais fraca que o Kerberos; assim, algumas organizações minimizam o uso de NTLM. Como resultado, o acesso ao Skype para Business Server pode ser restrito para interno ou clientes conectados por meio de uma conexão VPN ou DirectAccess. 
  
- **Protocolo Digest** para os chamados usuários anônimos. Usuários anônimos são usuários externos que não possuem credenciais reconhecidas do Active Directory, mas que foram convidados para uma conferência no local e possuem uma chave de conferência válida. A autenticação Digest não é usada para nenhuma outra interação do cliente.
    
Skype para autenticação de servidor de negócios consiste em duas fases:
  
1. Uma associação de segurança é estabelecida entre o cliente e o servidor.
    
2. O cliente e o servidor usam a associação de segurança existente para assinar mensagens enviadas e para verificar as mensagens recebidas. Mensagens não autenticadas de um cliente não são aceitas quando uma autenticação está habilitada no servidor.
    
Uma marca da confiança do usuário é anexada a cada mensagem originária de um usuário, não à identidade do usuário em si. O servidor verifica se há credenciais de usuário válidas em cada mensagem. Se as credenciais de usuário forem válidas, a mensagem não será contestada nem pelo primeiro servidor, nem pelos outros servidores da nuvem de servidores confiáveis.
  
Usuários com credenciais válidas emitidas por um parceiro federado são confiáveis, porém são opcionalmente impedidos por restrições adicionais de aproveitar toda a gama de privilégios concedidos aos usuários internos.
  
Os protocolos ICE e TURN também utilizam o mecanismo de desafio Digest, conforme descrito no IETF TURN RFC.
  
Certificados de cliente fornecem uma maneira alternativa dos usuários serem autenticados pelo Skype para Business Server. Em vez de fornecer um nome de usuário e senha, os usuários possuem um certificado e a chave privada correspondente ao certificado exigida para resolver um desafio criptográfico. (Esse certificado deve ter um nome de entidade ou nome alternativo da entidade que identifica o usuário e deve ser emitido por uma autoridade de certificação raiz confiável por servidores executando o Skype para Business Server, estar dentro do período de validade do certificado e não foi revogado.) Para ser autenticado, os usuários precisam apenas digitar um número de identificação pessoal (PIN). Os certificados são particularmente úteis para telefones, celulares e outros dispositivos onde é difícil inserir um nome de usuário e senha.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Requisitos criptográficos devido ao ASP .NET 4.5 

A partir do Skype para Business Server 2015 CU5, AES não é suportado para ASP.NET 4.6 e isso pode causar Skype App de reuniões não sejam iniciados. Se um cliente estiver usando o AES como o valor de validação de chave de máquina, você precisará redefinir o valor da chave de máquina SHA-1 ou outro algoritmo com suporte no nível do site Skype reuniões App no IIS. Se necessário, consulte [Gerenciamento de configuração do IIS 8.0 ASP.NET](https://docs.microsoft.com/en-us/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) para obter instruções.
  
Outros valores suportados são:
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
 Os valores AES, 3DES e MD5 não são permitidos, como costumavam no ASP.NET 4. [Aprimoramentos criptográficos no ASP.NET 4.5, pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) tem mais detalhes.
  
