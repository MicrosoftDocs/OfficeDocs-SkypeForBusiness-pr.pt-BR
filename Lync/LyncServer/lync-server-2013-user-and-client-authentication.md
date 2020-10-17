---
title: 'Lync Server 2013: autenticação de usuário e cliente'
description: 'Lync Server 2013: autenticação de usuário e de cliente.'
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
ms.openlocfilehash: ef545dda38e9ab4236e93df769ead393648194cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569807"
---
# <a name="user-and-client-authentication-for-lync-server-2013"></a>Autenticação de usuário e cliente para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-11_

Um usuário confiável é aquele cujas credenciais foram autenticadas por um servidor confiável no Microsoft Lync Server 2013. Esse servidor geralmente é um Standard Edition, Front-End Enterprise Edition ou Diretor. O Lync Server 2013 depende dos serviços de domínio do Active Directory como o repositório de back-end único e confiável das credenciais do usuário.

A autenticação é a provisão das credenciais do usuário em um servidor confiável. O Lync Server 2013 usa os seguintes protocolos de autenticação, dependendo do status e do local do usuário.

  - **Protocolo de segurança MIT Kerberos versão 5** para usuários internos com credenciais do Active Directory. O protocolo Kerberos requer conectividade de cliente com os Serviços de Domínio Active Directory; é por isso que ele não pode ser usado para autenticar clientes fora do firewall corporativo.

  - **Protocolo NTLM** para usuários com credenciais do Active Directory que se conectam em um ponto de extremidade fora do firewall corporativo. O serviço de Borda de Acesso passa as solicitações de logon para um Diretor, caso ele esteja presente, ou para um Servidor Front-End para fins de autenticação. O próprio serviço de Borda de Acesso não executa nenhuma autenticação.
    
    <div>
    

    > [!NOTE]  
    > O protocolo NTLM oferece proteção de ataque mais fraca do que Kerberos, para que algumas organizações minimizem o uso de NTLM. Como resultado, o acesso ao Lync Server 2013 pode ser restrito a clientes internos ou conectados por meio de uma conexão VPN ou do DirectAccess.

    
    </div>

  - **Protocolo Digest** para os chamados usuários anônimos. Os usuários anônimos são usuários externos que não têm credenciais reconhecidas do Active Directory, mas que foram convidados para uma conferência no local e possuem uma chave de conferência válida. A autenticação Digest não é usada para outras interações de cliente.

A autenticação do Lync Server 2013 consiste em duas fases:

1.  Uma associação de segurança é estabelecida entre o cliente e o servidor.

2.  O cliente e o servidor usam a associação de segurança existente para assinar as mensagens enviadas por eles e verificar as mensagens recebidas. As mensagens não autenticadas de um cliente não são aceitas quando a autenticação é habilitada no servidor.

A confiança de usuário é anexada a cada mensagem originada por um usuário, e não à própria identidade do usuário. O servidor verifica cada mensagem para saber se as credenciais do usuário são válidas. Se as credenciais do usuário forem válidas, a mensagem não será desafiada, não somente pelo primeiro servidor a recebê-la, mas por todos os outros servidores da gama de servidores confiáveis.

Os usuários com credenciais válidas emitidas por um parceiro federado são confiáveis, mas opcionalmente impedidas por restrições adicionais de usufruir da gama completa de privilégios acordados para os usuários internos.

Os protocolos ICE e TURN também usam o desafio Digest, conforme descrito no IETF TURN RFC.

Os certificados de cliente fornecem uma maneira alternativa para que os usuários sejam autenticados pelo Lync Server 2013. Em vez de fornecer um nome de usuário e senha, os usuários têm um certificado e a chave privada correspondente ao certificado necessário para resolver um desafio criptográfico. (Esse certificado deve ter um nome de entidade ou de assunto alternativo que identifique o usuário e deve ser emitido por uma autoridade de certificação raiz que é confiável para servidores que executam o Lync Server 2013, estando dentro do período de validade do certificado e não foram revogados.) Para ser autenticado, os usuários só precisam digitar um PIN (número de identificação pessoal). Os certificados são particularmente úteis para telefones e outros dispositivos que executam o Microsoft Lync 2013 Phone Edition, onde é difícil inserir um nome de usuário e/ou senha.

</div>

<span> </span>

</div>

</div>

</div>

