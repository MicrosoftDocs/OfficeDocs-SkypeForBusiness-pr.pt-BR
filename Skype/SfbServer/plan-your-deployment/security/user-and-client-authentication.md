---
title: Autenticação de usuário e de cliente para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Um usuário confiável é aquele cujas credenciais foram autenticadas por um servidor confiável no Skype for Business Server. Este servidor geralmente é um servidor Standard Edition, um servidor front-end da edição Enterprise ou um diretor. O Skype for Business Server depende dos serviços de domínio Active Directory como o repositório de back-end único confiável de credenciais do usuário.
ms.openlocfilehash: 35d1c6861ba8863e308939997fd802d4abcea404
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296865"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Autenticação de usuário e de cliente para o Skype for Business Server
 
Um usuário confiável é aquele cujas credenciais foram autenticadas por um servidor confiável no Skype for Business Server. Este servidor geralmente é um servidor Standard Edition, um servidor front-end da edição Enterprise ou um diretor. O Skype for Business Server depende dos serviços de domínio Active Directory como o repositório de back-end único confiável de credenciais do usuário.
  
Autenticação é o provisionamento de credenciais de usuário em um servidor confiável. O Skype for Business Server usa os seguintes protocolos de autenticação, dependendo do status e do local do usuário.
  
- **Protocolo de segurança MIT Kerberos versão 5** para usuários internos com credenciais do Active Directory. O Kerberos exige conectividade do cliente com os serviços de domínio Active Directory, o que é porque ele não pode ser usado para autenticar clientes fora do firewall corporativo.
    
- **Protocolo NTLM** para usuários com credenciais do Active Directory conectadas de um ponto de extremidade fora do firewall corporativo. O serviço de borda do Access passa solicitações de logon para um diretor, se estiver presente ou um servidor front-end para autenticação. O serviço de borda de acesso não realiza nenhuma autenticação.
    
    > [!NOTE]
    > O protocolo NTLM oferece proteção contra ataques mais fraca que o Kerberos; assim, algumas organizações minimizam o uso de NTLM. Como resultado, o acesso ao Skype for Business Server pode ser restrito a clientes internos ou conectados por meio de uma conexão VPN ou DirectAccess. 
  
- **Protocolo Digest** para os chamados usuários anônimos. Usuários anônimos são usuários externos que não possuem credenciais reconhecidas do Active Directory, mas que foram convidados para uma conferência no local e possuem uma chave de conferência válida. A autenticação Digest não é usada para nenhuma outra interação do cliente.
    
A autenticação do Skype for Business Server consiste em duas fases:
  
1. Uma associação de segurança é estabelecida entre o cliente e o servidor.
    
2. O cliente e o servidor usam a associação de segurança existente para assinar mensagens enviadas e para verificar as mensagens recebidas. Mensagens não autenticadas de um cliente não são aceitas quando uma autenticação está habilitada no servidor.
    
Uma marca da confiança do usuário é anexada a cada mensagem originária de um usuário, não à identidade do usuário em si. O servidor verifica se há credenciais de usuário válidas em cada mensagem. Se as credenciais de usuário forem válidas, a mensagem não será contestada nem pelo primeiro servidor, nem pelos outros servidores da nuvem de servidores confiáveis.
  
Usuários com credenciais válidas emitidas por um parceiro federado são confiáveis, porém são opcionalmente impedidos por restrições adicionais de aproveitar toda a gama de privilégios concedidos aos usuários internos.
  
Os protocolos ICE e TURN também utilizam o mecanismo de desafio Digest, conforme descrito no IETF TURN RFC.
  
Os certificados de cliente fornecem uma maneira alternativa para os usuários serem autenticados pelo Skype for Business Server. Em vez de fornecer um nome de usuário e senha, os usuários possuem um certificado e a chave privada correspondente ao certificado exigida para resolver um desafio criptográfico. (Esse certificado deve ter um nome de assunto ou um nome alternativo de assunto que identifique o usuário e deve ser emitido por uma autoridade de certificação raiz que seja confiável para servidores que executam o Skype for Business Server, seja dentro do período de validade do certificado e não foram revogados.) Para ser autenticado, os usuários só precisam digitar um PIN (número de identificação pessoal). Os certificados são particularmente úteis para telefones, celulares e outros dispositivos onde é difícil inserir um nome de usuário e senha.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Requisitos de criptografia devido ao ASP .NET 4,5 

A partir do Skype for Business Server 2015 CU5, o AES não é compatível com o ASP.NET 4,6, e isso pode fazer com que o aplicativo reuniões do Skype falhe ao iniciar. Se um cliente estiver usando AES como o valor de validação da chave do computador, será necessário redefinir o valor da chave do computador para SHA-1 ou outro algoritmo compatível no nível do site do aplicativo reuniões do Skype no IIS. Se necessário, consulte [Gerenciamento de configuração do ASP.net do IIS 8,0](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) para obter instruções.
  
Outros valores compatíveis são:
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  Os valores AES, 3DES e MD5 não são mais permitidos, como se estivessem em ASP.NET 4. [Melhorias criptográficas no ASP.NET 4,5, pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) tem mais detalhes.
  
