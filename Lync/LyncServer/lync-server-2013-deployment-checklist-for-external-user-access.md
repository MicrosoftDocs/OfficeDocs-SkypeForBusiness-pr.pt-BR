---
title: 'Lync Server 2013: lista de verificação de implantação para acesso de usuário externo'
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
ms.openlocfilehash: 5f2897434eb275b82ef9ab4ef78e32e99e8d0a5f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Lista de verificação de implantação para acesso de usuário externo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-04_

Antes de implantar sua rede de perímetro e implementar o suporte para usuários externos, você já deve ter implantado seus servidores internos do Microsoft Lync Server 2013, incluindo um pool de front-ends ou um servidor Standard Edition. Se você planeja implantar os directors opcionais em sua rede interna, você também deve implantá-los antes de implantar servidores de borda. Para obter detalhes sobre o processo de implantação do diretor, consulte [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) na documentação de planejamento.

O Microsoft Lync Server 2013 inclui ferramentas para facilitar o planejamento e a implantação de servidores internos e servidores de borda. Depois que a topologia estiver concluída, publique a definição de topologia resultante no seu ambiente de produção. Para tal, você precisa ser membro do grupo de **Administradores de domínio** e do grupo **RTCUniversalServerAdmins**.

  - **Ferramenta de planejamento**   o Office Communications Server 2007 R2 incluía uma ferramenta de planejamento e uma ferramenta de planejamento de borda que você poderia usar para ajudar a projetar o design de topologia. No Lync Server 2010, essas duas ferramentas foram combinadas em uma única ferramenta de planejamento com recursos e funcionalidades adicionais, como coletar contagem de usuário planejada, requisitos de voz, tipos de acesso de usuário externo e opções de Federação. Além disso, você pode planejar os parâmetros de rede da infraestrutura, como o endereço IP, tipos de balanceadores de carga e outras considerações de rede de perímetro.

  - **Construtor de topologias**   o construtor de topologias do Lync Server 2013 ajuda você a definir sua topologia e seus componentes. O construtor de topologias é essencial para implantar servidores que executam o Lync Server 2013. O construtor de topologias publica os resultados em um repositório de gerenciamento central que é usado para configurar todos os servidores que executam o Lync Server 2013 em sua organização. Não é possível instalar o Lync Server 2013 em servidores sem usar o construtor de topologias.

Se você criou sua topologia de borda durante o processo de planejamento, incluindo a execução do construtor de topologias para definir sua topologia de borda, você pode usar esses resultados para iniciar a implantação do servidor de borda. Se você não concluiu a criação da sua topologia de borda anteriormente ou deseja alterar as informações especificadas anteriormente, deverá concluir a execução do construtor de topologias antes de prosseguir com outras etapas de implantação. Para obter detalhes sobre como criar sua topologia, consulte [cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

Para obter detalhes sobre a ferramenta de planejamento e o construtor de topologias, consulte o [início do processo de planejamento do Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) na documentação de planejamento.

A tabela a seguir apresenta uma visão geral do processo de implantação do Servidor de Borda. Para revisar as decisões de planejamento que devem ser feitas antes de implantar o acesso de usuário externo, consulte [cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

<div>


> [!WARNING]  
> As informações na tabela a seguir destacam uma nova implantação. Se você tiver implantado servidores de borda em um ambiente do Lync Server 2010, Office Communications Server 2007 R2 ou Office Communications Server 2007, consulte a <A href="migration.md">migração</A> para obter detalhes sobre a migração para o Lync Server 2013. A migração não é suportada de nenhuma versão anterior ao Office Communications Server 2007 R2, incluindo o Office Communications Server 2007, o Live Communications Server 2005 e o Live Communications Server 2003.



</div>

Para aprimorar o desempenho e a segurança do Servidor de Borda e para facilitar a implantação, aplique as melhores práticas a seguir ao implantar sua rede de perímetro e Servidores de Borda:

  - Implante os servidores de borda somente depois de ter testado e verificado a operação do Lync Server 2013 dentro da sua organização.

  - Recomendamos que você implante os Servidores de Borda em um grupo de trabalho em vez de um domínio. Fazer isso simplifica a instalação e mantém os Serviços de Domínio de Diretório Ativo (AD DS) fora da rede de perímetro. Localizar os AD DS na rede de perímetro podem apresentar um risco à segurança significante.

  - Reunir um Servidor de Borda a um domínio localizado totalmente na rede de perímetro é suportado, mas não recomendado. Um servidor de Borda como parte de um domínio interno viola os limites de rede confiáveis, onde a Internet é o menos confiável, e o perímetro de rede é mais confiável que a Internet e a rede interna a mais confiável. Um servidor de Borda como membro do domínio é automaticamente uma parte da rede mais confiável, mas reside em uma rede menos confiável (o perímetro).

<div>

## <a name="deployment-process-for-edge-servers"></a>Processo de implantação para Servidores de Borda


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
<th>Permissions</th>
<th>Documentação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Criar a topologia de borda apropriada e determinar os componentes apropriados.</p></td>
<td><ul>
<li><p>Execute o construtor de topologias para definir as configurações do servidor de borda e criar e publicar a topologia e, em seguida, use o Shell de gerenciamento do Lync Server para exportar o arquivo de configuração da topologia.</p></li>
</ul></td>
<td><p>Grupo de <strong>Administradores de domínio</strong> e grupo <strong>RTCUniversalServerAdmins</strong> ou <strong>CsAdmins</strong></p>
<div>

> [!NOTE]  
> Você pode definir uma topologia usando uma conta que seja membro do grupo de usuários locais, mas a publicação de uma topologia requer uma conta que seja membro do grupo <STRONG>Admins. do Domínio</STRONG> e do grupo <STRONG>RTCUniversalServerAdmins</STRONG>.


</div></td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Criar uma topologia de borda e diretor no Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
<tr class="even">
<td><p>Preparar para instalação.</p></td>
<td><ol>
<li><p>Garanta que os pré-requisitos do sistema sejam atendidos.</p></li>
<li><p>Configure endereços IP (IPv4 e IPv6, se utilizados) para interfaces de rede internas e públicas em cada Servidor de Borda.</p></li>
<li><p>Configure registros DNS internos e externos (host A e AAAA para IPv4 e IPv6), incluindo a configuração do sufixo DNS no computador para ser implantado como um Servidor de Borda.</p></li>
<li><p>(Opcional) Crie e instale certificados públicos. O tempo necessário para obter certificados depende de qual CA (autoridade de certificação) emite o certificado. Se você não executar essa etapa neste ponto, você deverá fazê-lo durante a instalação do Servidor de Borda. O serviço de Servidor de Borda não pode ser iniciado enquanto os certificados não forem obtidos e instalados.</p></li>
<li><p>Forneça suporte para conectividade de IM pública, se a sua implantação for dar suporte a comunicações com usuários do Windows Live, AOL ou Yahoo!.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a se federar com o Yahoo! Messenger até a data de encerramento do serviço. Uma data de fim de vida de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</P>
> <LI>
> <P>O PIC USL é uma licença de assinatura por usuário por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo! Instantânea. A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual está se enrolando para baixo.</P>
> <LI>
> <P>Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</P></LI></UL>


</div></li>
<li><p>Provisione o suporte para XMPP e Federação do Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 Partners, se sua implantação usará esses</p></li>
<li><p>Configure firewalls.</p></li>
</ol></td>
<td><p>Conforme apropriado para sua organização</p></td>
<td><p><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparando para instalação de servidores na rede de perímetro do Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
<tr class="odd">
<td><p>Configurar proxy reverso.</p></td>
<td><ul>
<li><p>Configure o proxy reverso (por exemplo, para o Microsoft Forefront Threat Management Gateway 2010 ou o Microsoft Internet Security and Acceleration (ISA) Server com Service Pack 1) na rede de perímetro, obtenha os certificados públicos necessários e configure o regras de publicação na Web no servidor de proxy reverso.</p>
<p>Prepare o proxy reverso para serviços de Mobilidade se você tiver planejado para Mobilidade e está implantando serviços de Mobilidade no pool de Front End ou no servidor Standard Edition.</p></li>
</ul></td>
<td><p>Grupo <strong>Administrators</strong> ou administrador de Proxy Reversa</p></td>
<td><p><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configurando servidores de proxy reverso para o Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
<tr class="even">
<td><p>Configurar um Diretor (opcional).</p></td>
<td><ul>
<li><p>(Opcional) Instale e configure um ou mais Diretores na rede interna.</p></li>
</ul></td>
<td><p>Grupo <strong>Administradores</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-the-director.md">Configurando o diretor no Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
<tr class="odd">
<td><p>Configurar os Servidores de Borda.</p></td>
<td><ol>
<li><p>Instalar o software de pré-requisito</p></li>
<li><p>Transporte o arquivo de configuração de topologia exportado para cada Servidor de Borda.</p></li>
<li><p>Instale o software Lync Server 2013 em cada servidor de borda.</p></li>
<li><p>Configure os Servidores de Borda.</p></li>
<li><p>Solicite e instale certificados para cada Servidor de Borda.</p></li>
<li><p>Inicie os serviços dos Servidores de Borda.</p></li>
</ol></td>
<td><p>Grupo <strong>Administradores</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-edge-servers.md">Configurando servidores de borda no Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
<tr class="even">
<td><p>Configuração de implantação para acesso de usuário externo.</p></td>
<td><ol>
<li><p>Use o painel de controle do Lync Server para configurar o suporte para cada um dos seguintes (conforme aplicável):</p>
<ul>
<li><p>Retransmissão de mídia</p></li>
<li><p>Rota de federação</p></li>
<li><p>Acesso de usuários remotos</p></li>
<li><p>Federação com Lync Server, Office Communications Server e Live Communications Server</p></li>
<li><p>Conectividade a redes públicas de mensagens instantâneas</p></li>
<li><p>Federação XMPP</p></li>
<li><p>Usuários anônimos</p></li>
</ul></li>
<li><p>Configure contas de usuário para acesso de usuário remoto, federação, conectividade pública de IM, XMPP e suporte de usuário anônimo (conforme aplicável).</p></li>
</ol></td>
<td><p>Grupo <strong>RTCUniversalServerAdmins</strong> ou conta de usuário que é atribuído à função <strong>CSAdministrator</strong></p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurando o suporte para acesso de usuário externo no Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
<tr class="odd">
<td><p>Verificar sua configuração do Servidor de Borda.</p></td>
<td><ol>
<li><p>Verifique a conectividade de servidor e replicação de dados de configuração de servidores internos.</p></li>
<li><p>Verifique se os usuários externos podem se conectar, incluindo usuários remotos, usuários em domínios federados, usuários públicos de mensagens instantâneas e usuários anônimos, conforme apropriado para sua implantação.</p></li>
<li><p>Verificar a configuração e a comunicação usando o analisador de conectividade remota do Lync Server<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>Solução de problemas de dificuldades de configuração e comunicação</p></li>
</ol></td>
<td><p>Para verificação de replicação, o grupo <strong>RTCUniversalServerAdmins</strong> ou a conta de usuário que é atribuída à função <strong>CSAdministrator</strong></p>
<p>Para a verificação de conectividade de usuário, um usuário para cada tipo de acesso de usuário externo que você dê suporte.</p>
<p>Usuários remotos</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Verificando sua implantação de borda no Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

