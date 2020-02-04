---
title: 'Lync Server 2013: considerações de migração para reuniões'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af94514360509d4f608a21228b2fecf9a522007
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Considerações de migração para reuniões no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-10_

Os tópicos a seguir são discutidos nesta seção:

  - Alterações nas reuniões no Microsoft Lync Server 2013

  - Migrando usuários com base nas necessidades de conferência

  - Migrando reuniões e conteúdo de reunião existentes

  - Experiência do usuário durante a migração do Lync Server 2010

  - Experiência do usuário durante a migração do Office Communications Server 2007 R2

  - Compatibilidade do Microsoft Lync 2013 com reuniões em versões anteriores do servidor

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>Alterações nas reuniões no Lync Server 2013

**Recursos do Lync Server 2013.**    O Lync Server 2013 oferece novos recursos de conferência que se tornam disponíveis para os usuários após suas contas serem movidos para o Lync Server 2013 e que entram com o cliente Lync 2013. Novos recursos estão descritos nos [novos recursos de conferência do Lync server 2013](lync-server-2013-new-conferencing-features.md) e novidades [para clientes no Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**URL da reunião.**    Como no lync Server 2010, todas as reuniões agendadas recentemente no Lync Server 2013 têm um prefixo de URL de https://e as reuniões existentes são migradas juntamente com as contas de usuário. No entanto, o Lync Server 2013 não é compatível com a chamada em conferência do Office Communications Server 2007 R2 (prefixo da URL conf://) ou conferência via Web (prefixo da URL meet://). Consulte "migrando reuniões do Office Communications Server 2007 R2" mais adiante neste tópico para obter mais informações.

**Suporte ao cliente.**    Ao contrário do lync Server 2010, o Lync Server 2013 não é compatível com clientes do Office Communicator para conferência. Você não pode usar os seguintes clientes para ingressar em reuniões agendadas por meio do suplemento de reunião online do Lync 2013:

  - Office Communicator 2007 R2

  - Microsoft Office Communications Server 2007 R2 Attendant

  - Office Communicator 2007

  - Office Live Meeting 2007

Durante a migração, os usuários do Office Communicator 2007 R2 devem usar o Lync Web App 2013 para ingressar em reuniões do Lync Server 2013 até que seus clientes sejam atualizados. Observe que os usuários do Office Communicator 2007 R2 podem continuar a usar o cliente existente no Lync Server 2013 para recursos de presença e IM, mas os recursos de conferência não são compatíveis.

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>Migrando usuários com base nas necessidades de conferência

**Organizadores de reuniões frequentes.**    Considere migrar os organizadores de reunião frequentes no início do processo para que possam aproveitar os novos recursos do lync Server 2013 e do Lync 2013 descritos nos [novos recursos de conferência do Lync Server 2013](lync-server-2013-new-conferencing-features.md) e novidades [para clientes no Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**Usuários do Live Meeting.**    Se você estiver migrando do Office Communications Server 2007 R2 e tiver usuários que precisem de recursos de Webconferência específicos do Live Meeting, particularmente o suporte para reuniões grandes e salas de desativação, você terá as seguintes opções:

  - Organizadores de recomendação para usar o serviço Live Meeting, se disponível em sua organização.

  - Deixe os organizadores em casa na versão anterior do Office Communications Server, para que eles possam continuar a agendar conferências da Web de reunião ao vivo baseadas em servidor.

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>Migrando reuniões e conteúdo de reunião existentes

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>Migrando reuniões do Lync Server 2010

Quando você move um usuário do Lync Server 2010 para o Lync Server 2013, as seguintes informações se movem com a conta do usuário:

  - Reuniões já programadas pelo usuário. Isso inclui diretórios de conferência e dados de conferência.

  - O PIN (número de identificação pessoal) do usuário. O PIN atual do usuário continua a funcionar até que ele expire ou que o usuário solicitou um novo PIN.

No entanto, as seguintes informações da conta de usuário não se movem para o novo servidor:

  - Conteúdo da reunião, por exemplo, apresentações do PowerPoint, conteúdo do quadro de comunicações e dados de votação

Para mover o conteúdo que foi compartilhado em reuniões, use o parâmetro MoveMeetingContent do cmdlet Move-CsUser. Para obter detalhes sobre como usar esse cmdlet, consulte [move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) na documentação de cmdlets do Lync Server 2013.

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>Migrando reuniões do Office Communications Server 2007 R2

As reuniões do Office Communications Server 2007 R2 são chamadas em conferência (prefixo de URL conf://) ou conferências via Web (prefixo de URL meet://). O Lync Server 2013 não é compatível com essas conferências anteriores do conf://e do meet://, e elas não são migradas juntamente com a conta do usuário. Após a migração, você deve instruir os usuários a atualizar os links para todas as reuniões online agendadas. Isso pode fazer isso após a instalação do cliente do Lync 2013 abrindo um convite de reunião agendada, que atualiza a URL da reunião, e reenvia o convite aos participantes.

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>Experiência do usuário durante a migração do Lync Server 2010

Esta seção fornece um resumo da experiência de Conferência dos usuários durante a migração do Lync 2010. Para obter mais detalhes sobre como os clientes do Lync Server 2013 podem coexistir e interagir com versões anteriores do cliente e do servidor, consulte [interoperabilidade do cliente no Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>Ingressando em reuniões do Lync Server 2010 com um cliente do Lync 2013

Durante a migração do Lync Server 2010, pode haver um período de coexistência quando os usuários ingressam em reuniões do Lync Server 2010 com um cliente Lync 2013. Esses usuários têm acesso aos recursos do cliente do Lync 2013 com as seguintes exceções:

  - Nas opções de gerenciamento de **participantes** , que podem ser acessadas apontando para o ícone pessoas na janela da reunião, a opção **nenhuma mensagem instantânea de reunião** não funciona.

  - O modo de exibição de galeria não funciona em videoconferências. O usuário vê apenas o alto-falante ativo em vez de todos os alto-falantes. Na lista de opções **escolher um layout** , o **modo de exibição Galeria** não está disponível

  - A lista de participantes é exibida por padrão em videoconferências.

  - Ao clicar com o botão direito do mouse em um usuário na lista de participantes, o botão **bloquear as opções de gerenciamento de participantes do vídeo** e **fixar em Galeria** não estará disponível.

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Experiência do usuário durante a migração do Office Communications Server 2007 R2

Esta seção fornece um resumo da experiência de Conferência dos usuários ao migrar do Office Communications Server 2007 R2, antes e depois que o Lync 2013 está instalado. Para obter mais detalhes sobre como os clientes do Lync Server 2013 podem coexistir e interagir com versões anteriores do cliente e do servidor, consulte [interoperabilidade do cliente no Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>Após a migração da conta de usuário, antes que o Lync 2013 seja instalado

Após a migração de um usuário para o servidor do Lync Server 2013, mas antes de novos clientes serem instalados, os usuários do Office Communicator 2007 R2 podem continuar a usar o cliente existente no Lync Server 2013 para recursos de presença e IM, mas os recursos de conferência não são suporte.

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>Após a migração da conta de usuário, após a instalação do Lync 2013

Quando um usuário migrado instalar o Lync 2013, o suplemento de reunião online do Lync 2013 também será instalado. Isso tem os seguintes efeitos:

  - Todas as reuniões agendadas subsequentemente usam o novo formato de reunião, que usa um endereço https://em vez do endereço herdado do Live Meeting do meet://.

  - Em uma implantação gerenciada por ti do Lync 2013, o administrador tem a opção de desinstalar o suplemento de conferência do Microsoft Office Outlook, que é usado para agendar reuniões com base em serviço e servidor de reunião ao vivo. No entanto, você pode ter usuários que precisam continuar a agendar reuniões do serviço Live Meeting. Nesse caso, você pode permitir que ambos os suplementos coexistam.

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>Reuniões com organizações federadas que usam clientes anteriores

Os usuários de organizações federadas que estiverem usando o Microsoft Office Communicator 2007 não poderão ingressar em reuniões do Lync Server 2013 em sua organização se essas reuniões estiverem bloqueadas pelo organizador. Você precisa reagendar essas reuniões no Lync Server 2013 para que os participantes federados ingressem na reunião usando a nova URL de reunião do https://, eles podem usar o Lync Web App.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

