---
title: 'Lync Server 2013: configurar adaptadores de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 662ad7425a248148e9e2dde0c8f18ccea5add0c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520558"
---
# <a name="configure-network-adapters-in-lync-server-2013"></a>Configurar adaptadores de rede no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-07_

Você deve atribuir um ou mais endereços IP ao adaptador de rede externo e pelo menos um endereço IP ao adaptador de rede interno.

Nos procedimentos a seguir, o servidor que executa o Forefront Threat Management Gateway (TMG) 2010 ou o roteamento de solicitação de aplicativo do servidor de informações da Internet tem dois adaptadores de rede:

  - Um adaptador de rede público ou externo, para clientes que tentam se conectar ao seu site (ou seja, geralmente pela Internet).

  - Uma interface de rede privada ou interna, para servidores internos que executam o Lync Server que hospeda serviços Web.

<div>


> [!IMPORTANT]  
> Semelhante aos servidores de borda, você define o gateway padrão somente no adaptador de rede externo. O gateway padrão será o endereço IP do roteador ou do firewall externo voltado para direcionar o tráfego para a Internet. Para o tráfego destinado do proxy reverso para o adaptador de rede interno, você deve usar rotas estáticas persistentes (como o comando Route no Windows Server) para todas as sub-redes que contêm servidores referenciados pelas regras de publicação da Web. A definição de uma rota persistente não faz com que o computador se torne um roteador. Se o encaminhamento de IP não estiver habilitado, o computador estará agindo somente para direcionar o tráfego específico destinado a outra rede para a interface apropriada. Isso é essencialmente Configurando dois gateways – um como o padrão apontando para as redes externas e outra para o tráfego destinado à interface interna e em um roteador ou outra rede.<BR>No entanto, a criação de rotas persistentes para todas as sub-redes pode não ser necessária se os roteadores da rede estiverem configurados para resumir as rotas. Criar uma rota persistente para a rede onde o roteador está definido e usar o roteador como o gateway padrão. Se você não tiver certeza de que sua rede está configurada e precisa de orientação sobre quais rotas persistentes precisam ser criadas, consulte os engenheiros de rede da sua empresa.<BR>O proxy reverso deve ser capaz de resolver os registros de host DNS (A) para o diretor interno ou servidor front-end e FQDNs do pool de próximo salto usados nas regras de publicação da Web. Como nos servidores de borda, por motivos de segurança, recomendamos que você não configure um proxy reverso para usar um servidor DNS localizado na rede interna. Isso significa que você precisa dos servidores DNS no perímetro ou precisa de entradas de arquivo HOSTs no proxy reverso que resolva cada um desses FQDNs para o endereço IP interno dos servidores.



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a>Para configurar as placas adaptadoras de rede no computador proxy reverso

1.  No servidor Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2 em execução como proxy reverso, clique em **Change Adapter Settings** **Iniciar**, aponte para **painel de controle**, clique em **centro de rede e compartilhamento**e, em seguida, clique em **alterar as configurações do adaptador**.

2.  Clique com o botão direito do mouse na conexão de rede externa que você deseja usar para a interface externa e clique em **Propriedades**.

3.  Na página **Propriedades** , clique na guia **rede** , clique em **protocolo TCP/IP versão 4 (TCP/IPv4)** na lista **esta conexão usa os seguintes itens** e clique em **Propriedades**.

4.  Na página **Propriedades do protocolo TCP/IP** , configure os endereços IP conforme apropriado para a sub-rede de rede à qual o adaptador de rede está conectado.
    
    <div>
    

    > [!NOTE]  
    > Se o proxy reverso já estiver sendo usado por outros aplicativos que usam HTTPS/TCP/443, por exemplo, para publicar o Outlook Web Access, é necessário adicionar outro endereço IP para que você possa publicar os serviços Web do Lync Server 2013 em HTTPS/TCP/443 sem interferir nas regras existentes e ouvintes da Web, ou você precisa substituir o certificado existente por um que adicione os novos nomes de FQDN externos ao nome alternativo da entidade.

    
    </div>

5.  Clique em **OK**e, em seguida, clique em **OK**.

6.  Em **conexões de rede**, clique com o botão direito do mouse na conexão de rede interna que você deseja usar para a interface interna e, em seguida, clique em **Propriedades**.

7.  Repita as etapas de 3 a 5 para configurar a conexão de rede interna.

</div>

</div>

<span> </span>

</div>

</div>

</div>

