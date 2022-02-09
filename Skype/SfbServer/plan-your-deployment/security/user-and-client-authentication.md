---
title: Autenticação de usuário e cliente para Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Um usuário confiável é aquele cujas credenciais foram autenticadas por um servidor confiável em Skype for Business Server. Esse servidor geralmente é um Standard Edition, Front-End Enterprise Edition ou Diretor. Skype for Business Server se baseia nos Serviços de Domínio do Active Directory como o repositório único e confiável de credenciais de usuário.
ms.openlocfilehash: b18d07a8cb0b427cf7cceb0fd81c8d657c98b7a1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401705"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Autenticação de usuário e cliente para Skype for Business Server
 
Um usuário confiável é aquele cujas credenciais foram autenticadas por um servidor confiável em Skype for Business Server. Esse servidor geralmente é um Standard Edition, Front-End Enterprise Edition ou Diretor. Skype for Business Server se baseia nos Serviços de Domínio do Active Directory como o repositório único e confiável de credenciais de usuário.
  
A autenticação é a provisão das credenciais do usuário em um servidor confiável. Skype for Business Server usa os seguintes protocolos de autenticação, dependendo do status e do local do usuário.
  
- **Protocolo de segurança MIT Kerberos versão 5** para usuários internos com credenciais do Active Directory. O protocolo Kerberos requer conectividade de cliente com os Serviços de Domínio Active Directory; é por isso que ele não pode ser usado para autenticar clientes fora do firewall corporativo.
    
- **Protocolo NTLM** para usuários com credenciais do Active Directory que se conectam em um ponto de extremidade fora do firewall corporativo. O serviço de Borda de Acesso passa as solicitações de logon para um Diretor, caso ele esteja presente, ou para um Servidor Front-End para fins de autenticação. O próprio serviço de Borda de Acesso não executa nenhuma autenticação.
    
    > [!NOTE]
    > O protocolo NTLM oferece proteção de ataque mais fraca do que Kerberos, portanto, algumas organizações minimizam o uso de NTLM. Como resultado, o acesso ao Skype for Business Server pode ser restrito a clientes internos ou conectados por meio de uma conexão VPN ou DirectAccess. 
  
- **Protocolo Digest** para os chamados usuários anônimos. Os usuários anônimos são usuários externos que não têm credenciais reconhecidas do Active Directory, mas que foram convidados para uma conferência no local e possuem uma chave de conferência válida. A autenticação Digest não é usada para outras interações de cliente.
    
Skype for Business Server autenticação consiste em duas fases:
  
1. Uma associação de segurança é estabelecida entre o cliente e o servidor.
    
2. O cliente e o servidor usam a associação de segurança existente para assinar as mensagens enviadas por eles e verificar as mensagens recebidas. As mensagens não autenticadas de um cliente não são aceitas quando a autenticação é habilitada no servidor.
    
A confiança de usuário é anexada a cada mensagem originada por um usuário, e não à própria identidade do usuário. O servidor verifica cada mensagem para saber se as credenciais do usuário são válidas. Se as credenciais do usuário forem válidas, a mensagem não será desafiada, não somente pelo primeiro servidor a recebê-la, mas por todos os outros servidores da gama de servidores confiáveis.
  
Os usuários com credenciais válidas emitidas por um parceiro federado são confiáveis, mas opcionalmente impedidas por restrições adicionais de usufruir da gama completa de privilégios acordados para os usuários internos.
  
Os protocolos ICE e TURN também usam o desafio Digest, conforme descrito no IETF TURN RFC.
  
Os certificados de cliente fornecem uma maneira alternativa para que os usuários sejam autenticados por Skype for Business Server. Em vez de fornecer um nome de usuário e uma senha, os usuários têm um certificado e a chave privada correspondentes ao certificado necessário para resolver um desafio criptográfico. (Esse certificado deve ter um nome de assunto ou um nome alternativo de assunto que identifique o usuário e deve ser emitido por uma AC Raiz confiável por servidores que executam Skype for Business Server, estar dentro do período de validade do certificado e não ter sido revogado.) Para serem autenticados, os usuários só precisam digitar um PIN (número de identificação pessoal). Os certificados são particularmente úteis para telefones, telefones celulares e outros dispositivos onde é difícil inserir um nome de usuário e uma senha.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Requisitos criptográficos devido ASP.NET 4.5 

A partir do Skype for Business Server 2015 CU5, o AES não tem suporte para o ASP.NET 4.6 e isso pode fazer com que o aplicativo de reuniões do Skype falhe no início. Se um cliente estiver usando o AES como o valor de validação de chave de máquina, você precisará redefinir o valor da chave do computador para SHA-1 ou outro algoritmo com suporte no nível do site do aplicativo reuniões Skype reuniões no IIS. Se necessário, consulte [IIS 8.0 ASP.NET Configuration Management](/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) para obter instruções.
  
Outros valores com suporte são:
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  Os valores AES, 3DES e MD5 não são mais permitidos, pois eles já estavam ASP.NET 4. [Melhorias criptográficas ASP.NET 4.5, pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) tem mais detalhes.
