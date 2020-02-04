---
title: 'Lync Server 2013: Llista de verificação de implantação para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad2ad90ab43402babdd10478e1d86cac2a38ddf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Llista de verificação de implantação para acesso de usuário externo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-04_

Antes de implantar a sua rede de perímetro e implementar o suporte para usuários externos, você já deve ter implantado seus servidores internos do Microsoft Lync Server 2013, incluindo um pool de front-ends ou um servidor Standard Edition. Se você planeja implantar os diretores opcionais na sua rede interna, também deve implantá-los antes de implantar servidores de borda. Para obter detalhes sobre o processo de implantação do diretor, consulte [cenários do diretor do Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) na documentação de planejamento.

O Microsoft Lync Server 2013 inclui ferramentas para facilitar o planejamento e a implantação de servidores internos e de servidores de borda. Após a conclusão da topologia, publique a definição de topologia resultante em seu ambiente de produção. Para fazer isso, você deve ser membro do grupo **Domain admins** e do grupo **RTCUniversalServerAdmins** .

  - **Ferramenta de planejamento**   o Office Communications Server 2007 R2 incluía uma ferramenta de planejamento e uma ferramenta de planejamento de borda que você pode usar para ajudar a orientar o design da topologia. No Lync Server 2010, essas duas ferramentas foram combinadas em uma única ferramenta de planejamento que tem recursos e funcionalidades adicionais, como coletar contagem de usuários, requisitos de voz, tipos de acesso de usuário externo e opções de Federação. Além disso, você pode planejar os parâmetros de rede de sua infraestrutura, como endereços IP, tipos de balanceador de carga e outras considerações de rede do perímetro.

  - **Construtor Topology Builder**   o construtor de topologias do Lync Server 2013 ajuda você a definir sua topologia e seus componentes. O construtor de topologias é essencial para implantar servidores que executam o Lync Server 2013. O construtor de topologias publica os resultados em um repositório de gerenciamento central que é usado para configurar todos os servidores que executam o Lync Server 2013 em sua organização. Não é possível instalar o Lync Server 2013 em servidores sem usar o construtor de topologias.

Se você tiver projetado a topologia de borda durante o processo de planejamento, incluindo a execução do construtor de topologias para definir sua topologia de borda, você pode usar esses resultados para iniciar a implantação do servidor de borda. Se você não concluiu a criação da sua topologia de borda anteriormente ou deseja alterar as informações especificadas anteriormente, deverá concluir a execução do construtor de topologias antes de prosseguir com outras etapas de implantação. Para obter detalhes sobre como criar sua topologia, consulte [cenários para acesso de usuários externos no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

Para obter detalhes sobre a ferramenta de planejamento e o construtor de topologias, consulte [iniciar o processo de planejamento do Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) na documentação de planejamento.

A tabela a seguir fornece uma visão geral do processo de implantação do servidor de borda. Para revisar as decisões de planejamento que devem ser tomadas antes de implantar o acesso de usuários externos, consulte [cenários para acesso de usuários externos no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

<div>


> [!WARNING]  
> As informações na tabela a seguir se concentram em uma nova implantação. Se você implantou servidores de borda em um ambiente do Lync Server 2010, do Office Communications Server 2007 R2 ou do Office Communications Server 2007, consulte a <A href="migration.md">migração</A> para obter detalhes sobre a migração para o Lync Server 2013. Não há suporte para a migração de nenhuma versão anterior ao Office Communications Server 2007 R2, incluindo o Office Communications Server 2007, o Live Communications Server 2005 e o Live Communications Server 2003.



</div>

Para melhorar o desempenho e a segurança do servidor de borda e facilitar a implantação, aplique as seguintes práticas recomendadas ao implantar seus servidores de rede de perímetro e de borda:

  - Implante os servidores de borda somente depois de testar e verificar a operação do Lync Server 2013 dentro da sua organização.

  - Recomendamos que você implante os servidores de borda em um grupo de trabalho em vez de um domínio. Isso simplifica a instalação e mantém os serviços de domínio Active Directory (AD DS) fora da rede de perímetro. Localizar o AD DS na rede de perímetro pode apresentar um risco de segurança significativo.

  - Ingressar em um servidor de borda em um domínio localizado inteiramente na rede de perímetro é compatível, mas não é recomendado. Um servidor de borda como parte do domínio interno viola os limites de rede confiáveis, em que a Internet é menos confiável, a rede de perímetro é mais confiável do que a Internet, e a rede interna é mais confiável. Um servidor de borda como membro do domínio é automaticamente parte da rede mais confiável, mas reside em uma rede menos confiável (o perímetro).

<div>

## <a name="deployment-process-for-edge-servers"></a>Processo de implantação para servidores de borda


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Etapas</th>
<th>Permissões</th>
<th>Documentação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Crie a topologia de borda apropriada e determine os componentes apropriados.</p></td>
<td><ul>
<li><p>Execute o construtor de topologias para definir as configurações do servidor de borda e criar e publicar a topologia e, em seguida, use o Shell de gerenciamento do Lync Server para exportar o arquivo de configuração de topologia.</p></li>
</ul></td>
<td><p>Grupo <strong>Administradores de domínio</strong> e grupo <strong>RTCUniversalServerAdmins</strong> ou <strong>CsAdmins</strong></p>
<div>

> [!NOTE]  
> Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas publicar uma topologia requer uma conta que seja membro do grupo <STRONG>Domain admins</STRONG> e do grupo <STRONG>RTCUniversalServerAdmins</STRONG> .


</div></td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Criando uma topologia de Edge e Director no Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
<tr class="even">
<td><p>Prepare-se para a instalação.</p></td>
<td><ol>
<li><p>Certifique-se de que os pré-requisitos do sistema sejam atendidos.</p></li>
<li><p>Configurar endereços IP (IPv4 e IPv6, se usados) para interfaces de rede internas e públicas voltadas para cada servidor de borda.</p></li>
<li><p>Configurar registros DNS internos e externos (host A e AAAA para IPv4 e IPv6), incluindo a configuração do sufixo DNS no computador a ser implantado como um servidor de borda.</p></li>
<li><p>Adicionais Criar e instalar certificados públicos. O tempo necessário para obter certificados depende de qual a autoridade de certificação (CA) emite o certificado. Se você não executar esta etapa neste ponto, deverá fazê-lo durante a instalação do servidor de borda. Os serviços de servidor de borda não podem ser iniciados até que os certificados sejam obtidos e instalados.</p></li>
<li><p>Provisionar o suporte para conectividade de IM pública, se sua implantação for dar suporte a comunicações com o Windows Live, AOL ou Yahoo! Eles.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo! Messenger até a data de encerramento do serviço. Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.</P>
> <LI>
> <P>O PIC USL é uma licença de assinatura por usuário por mês necessária para o Lync Server ou o Office Communications Server se federar com o Yahoo! Spam. A capacidade da Microsoft de oferecer esse serviço por meio do suporte do Yahoo!, o contrato subjacente para o qual está prestes a ser enrolado.</P>
> <LI>
> <P>Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com mensagens instantâneas e voz.</P></LI></UL>


</div></li>
<li><p>Provisionar suporte para XMPP e suporte de Federação para o Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 Partners, se a sua implantação usar esses</p></li>
<li><p>Configurar firewalls.</p></li>
</ol></td>
<td><p>Conforme apropriado para a sua organização</p></td>
<td><p><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparando para a instalação de servidores na rede de perímetro do Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
<tr class="odd">
<td><p>Configurar o proxy reverso.</p></td>
<td><ul>
<li><p>Configurar o proxy inverso (por exemplo, para Microsoft Forefront Threat Management Gateway 2010 ou Microsoft Internet Security and Acceleration (ISA) Server with Service Pack 1) na rede de perímetro, obter os certificados públicos necessários e configurar o regras de publicação na Web no servidor proxy reverso.</p>
<p>Prepare o proxy reverso para serviços de mobilidade se você tiver planejado para a mobilidade e estiver implantando os serviços de mobilidade no pool de front-ends ou no servidor Standard Edition.</p></li>
</ul></td>
<td><p>Grupo <strong>Administradores</strong> ou administrador de proxy reverso</p></td>
<td><p><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configurando servidores proxy inversos para o Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
<tr class="even">
<td><p>Configurar um diretor (opcional).</p></td>
<td><ul>
<li><p>Adicionais Instale e configure um ou mais directors na rede interna.</p></li>
</ul></td>
<td><p>Grupo <strong>Administradores</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-the-director.md">Configurando o diretor do Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
<tr class="odd">
<td><p>Configurar servidores de borda.</p></td>
<td><ol>
<li><p>Instale o software de pré-requisito.</p></li>
<li><p>Transportar o arquivo de configuração de topologia exportado para cada servidor de borda.</p></li>
<li><p>Instale o software do Lync Server 2013 em cada servidor de borda.</p></li>
<li><p>Configurar os servidores de borda.</p></li>
<li><p>Solicitar e instalar certificados para cada servidor de borda.</p></li>
<li><p>Inicie os serviços do servidor de borda.</p></li>
</ol></td>
<td><p>Grupo <strong>Administradores</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-edge-servers.md">Configurando servidores de borda no Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
<tr class="even">
<td><p>Configurar a implantação para acesso ao usuário externo.</p></td>
<td><ol>
<li><p>Use o painel de controle do Lync Server para configurar o suporte para cada um dos seguintes (conforme aplicável):</p>
<ul>
<li><p>Retransmissão de mídia</p></li>
<li><p>Roteiro de Federação</p></li>
<li><p>Acesso de usuário remoto</p></li>
<li><p>Federação com o Lync Server, o Office Communications Server e o Live Communications Server</p></li>
<li><p>Conectividade de mensagem de chat Pública</p></li>
<li><p>Federação do XMPP</p></li>
<li><p>Usuários anônimos</p></li>
</ul></li>
<li><p>Configurar contas de usuário para acesso de usuário remoto, Federação, conectividade de mensagem de chat pública, suporte a XMPP e usuários anônimos (conforme aplicável)</p></li>
</ol></td>
<td><p>Grupo <strong>RTCUniversalServerAdmins</strong> ou conta de usuário atribuída à função <strong>CSAdministrator</strong></p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurando o suporte para acesso de usuários externos no Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
<tr class="odd">
<td><p>Verifique a configuração do servidor de borda.</p></td>
<td><ol>
<li><p>Verifique a conectividade do servidor e a replicação de dados de configuração de servidores internos.</p></li>
<li><p>Verifique se usuários externos podem se conectar, incluindo usuários remotos, usuários em domínios federados, usuários de mensagens de chat públicas e usuários anônimos, conforme apropriado para a sua implantação.</p></li>
<li><p>Verificar a configuração e a comunicação usando o analisador de conectividade remota do Lync Server<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>Solucionar problemas de configuração e dificuldade de comunicação</p></li>
</ol></td>
<td><p>Para verificar a replicação, grupo <strong>RTCUniversalServerAdmins</strong> ou conta de usuário atribuída à função <strong>CSAdministrator</strong></p>
<p>Para verificar a conectividade do usuário, um usuário para cada tipo de acesso de usuário externo ao qual você dá suporte</p>
<p>Usuários remotos</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Verificando a implantação de borda no Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

