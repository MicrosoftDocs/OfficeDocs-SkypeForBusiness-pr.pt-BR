---
title: 'Lync Server 2013: autenticação de usuário e cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c9c91f1b8355c95ceb3deae5f07e5c95710d036
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a>Autenticação de usuário e cliente para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-11_

Um usuário confiável é aquele cujas credenciais foram autenticadas por um servidor confiável no Microsoft Lync Server 2013. Este servidor geralmente é um servidor Standard Edition, um servidor front-end da edição Enterprise ou um diretor. O Lync Server 2013 depende dos serviços de domínio Active Directory como o repositório de back-end único confiável de credenciais do usuário.

Autenticação é o provisionamento de credenciais de usuário em um servidor confiável. O Lync Server 2013 usa os seguintes protocolos de autenticação, dependendo do status e do local do usuário.

  - **Protocolo de segurança MIT Kerberos versão 5** para usuários internos com credenciais do Active Directory. O Kerberos exige conectividade do cliente com os serviços de domínio Active Directory, o que é porque ele não pode ser usado para autenticar clientes fora do firewall corporativo.

  - **Protocolo NTLM** para usuários com credenciais do Active Directory conectadas de um ponto de extremidade fora do firewall corporativo. O serviço de borda do Access passa solicitações de logon para um diretor, se estiver presente ou um servidor front-end para autenticação. O serviço de borda de acesso não realiza nenhuma autenticação.
    
    <div>
    

    > [!NOTE]  
    > O protocolo NTLM oferece proteção contra ataques mais fraca que o Kerberos; assim, algumas organizações minimizam o uso de NTLM. Como resultado, o acesso ao Lync Server 2013 pode estar restrito a clientes internos ou a clientes conectados por meio de uma conexão VPN ou DirectAccess.

    
    </div>

  - **Protocolo Digest** para os chamados usuários anônimos. Usuários anônimos são usuários externos que não possuem credenciais reconhecidas do Active Directory, mas que foram convidados para uma conferência no local e possuem uma chave de conferência válida. A autenticação Digest não é usada para nenhuma outra interação do cliente.

A autenticação do Lync Server 2013 consiste em duas fases:

1.  Uma associação de segurança é estabelecida entre o cliente e o servidor.

2.  O cliente e o servidor usam a associação de segurança existente para assinar mensagens enviadas e para verificar as mensagens recebidas. Mensagens não autenticadas de um cliente não são aceitas quando uma autenticação está habilitada no servidor.

Uma marca da confiança do usuário é anexada a cada mensagem originária de um usuário, não à identidade do usuário em si. O servidor verifica se há credenciais de usuário válidas em cada mensagem. Se as credenciais de usuário forem válidas, a mensagem não será contestada nem pelo primeiro servidor, nem pelos outros servidores da nuvem de servidores confiáveis.

Usuários com credenciais válidas emitidas por um parceiro federado são confiáveis, porém são opcionalmente impedidos por restrições adicionais de aproveitar toda a gama de privilégios concedidos aos usuários internos.

Os protocolos ICE e TURN também utilizam o mecanismo de desafio Digest, conforme descrito no IETF TURN RFC.

Os certificados de cliente fornecem uma maneira alternativa para os usuários serem autenticados pelo Lync Server 2013. Em vez de fornecer um nome de usuário e senha, os usuários possuem um certificado e a chave privada correspondente ao certificado exigida para resolver um desafio criptográfico. (Esse certificado deve ter um nome de assunto ou um nome alternativo de assunto que identifique o usuário e deve ser emitido por uma autoridade de certificação raiz que seja confiável para os servidores que executam o Lync Server 2013, estando dentro do período de validade do certificado e não foram revogados.) Para ser autenticado, os usuários só precisam digitar um PIN (número de identificação pessoal). Os certificados são especialmente úteis para telefones e outros dispositivos que executam o Microsoft Lync 2013 Phone Edition, no qual é difícil digitar um nome de usuário e/ou senha.

</div>

<span> </span>

</div>

</div>

</div>

