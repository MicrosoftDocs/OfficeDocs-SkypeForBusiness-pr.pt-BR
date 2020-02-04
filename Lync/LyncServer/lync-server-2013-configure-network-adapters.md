---
title: 'Lync Server 2013: Configurar adaptadores de rede'
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
ms.openlocfilehash: 30889a6b145e7256a313c4deedafc74d99499719
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a>Configurar adaptadores de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-07_

Você deve atribuir um ou mais endereços IP ao adaptador de rede externo e ao menos um endereço IP ao adaptador de rede interno.

Nos procedimentos a seguir, o servidor que executa o Forefront Threat Management Gateway (TMG) 2010 ou o roteamento de solicitação de aplicativo do Internet Information Server tem dois adaptadores de rede:

  - Um adaptador de rede público ou externo, para clientes que tentam se conectar ao seu website (ou seja, geralmente pela Internet).

  - Uma interface de rede privada ou interna, para servidores internos que executam o Lync Server que hospeda serviços Web.

<div>


> [!IMPORTANT]  
> Da mesma forma que os servidores de borda, você define o gateway padrão somente no adaptador de rede externo. O gateway padrão será o endereço IP do roteador ou o firewall de face externo que direcionará o tráfego para a Internet. Para o tráfego destinado ao proxy inverso para o adaptador de rede de face interna, você deve usar rotas estáticas persistentes (como o comando Route no Windows Server) para todas as sub-redes contendo servidores referenciados pelas regras de publicação na Web. A configuração de uma rota persistente não faz com que o computador se torne um roteador. Se o encaminhamento de IP não estiver habilitado, o computador estará agindo somente para direcionar o tráfego específico destinado a outra rede para a interface apropriada. Isso é essencialmente Configurando dois gateways – um como padrão para as redes externas e outro para o tráfego destinado à interface interna e em um roteador ou outra rede.<BR>No entanto, a criação de rotas persistentes para todas as sub-redes pode não ser necessária se os roteadores da sua rede estiverem configurados para resumir as rotas. Crie uma rota persistente para a rede na qual o roteador está definido e use o roteador como o gateway padrão. Se você não tiver certeza de como sua rede está configurada e precisar de orientação sobre quais rotas persistentes precisam ser criadas, consulte os engenheiros de rede da sua empresa.<BR>O proxy reverso deve ser capaz de resolver os registros de host DNS (A) para o diretor interno ou o servidor front-end e os FQDNs dos próximos pools de saltos usados nas regras de publicação na Web. Assim como nos servidores de borda, por motivos de segurança, recomendamos que você não configure um proxy reverso para usar um servidor DNS localizado na rede interna. Isso significa que você precisa de servidores DNS no perímetro ou precisa de entradas de arquivos de host no proxy reverso que resolva cada um desses FQDNs para o endereço IP interno dos servidores.



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a>Para configurar os cartões adaptadores de rede no computador proxy reverso

1.  Nos servidores Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2 sendo executados como proxy reverso, abra **alterar as configurações do adaptador** clicando em **Iniciar**, apontando para **painel de controle**, clicando em Central de **rede e compartilhamento**e, em seguida, clicando em **alterar as configurações do adaptador**.

2.  Clique com o botão direito do mouse na conexão de rede externa que você deseja usar para a interface externa e, em seguida, clique em **Propriedades**.

3.  Na página **Propriedades** , clique na guia **rede** , clique em **protocolo de Internet versão 4 (TCP/IPv4)** na lista **esta conexão usa a lista de itens a seguir** e, em seguida, clique em **Propriedades**.

4.  Na página **Propriedades de protocolo TCP/IP** , configure os endereços IP conforme apropriado para a sub-rede da rede à qual o adaptador de rede está conectado.
    
    <div>
    

    > [!NOTE]  
    > Se o proxy reverso já estiver sendo usado por outros aplicativos que usam HTTPS/TCP/443, por exemplo para publicação do Outlook Web Access, você precisa adicionar outro endereço IP para poder publicar os serviços Web do Lync Server 2013 em HTTPS/TCP/443 sem interferir nas regras existentes e ouvintes da Web, ou precisa substituir o certificado existente por um que adicione os novos nomes de FQDN externos ao nome alternativo da entidade.

    
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

