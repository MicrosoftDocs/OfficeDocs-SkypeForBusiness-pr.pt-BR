---
title: 'Lync Server 2013: criar ou modificar uma política de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc01c8bed503f06806c873431ef201e03c31811
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516888"
---
# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a>Criar ou modificar uma política de conferência no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-07_

Siga estas etapas para criar uma política de conferência no nível do usuário ou no nível do site. Para obter detalhes sobre como atribuir uma política de nível de usuário a um usuário, consulte [atribuir uma política de conferência por usuário no Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md). Para obter uma lista de todas as configurações de política de conferência disponíveis, consulte [referência de configurações de política de conferência para o Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>

## <a name="to-create-a-new-user-or-site-policy"></a>Para criar uma nova política de usuário ou de site

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Conferência** e em **Política de Conferência**.

4.  Clique em **Nova** e execute um dos seguintes procedimentos:
    
      - Para criar uma política de nível de usuário, clique em **Política de usuário**. Em **Nova Política de Conferências**, em **Nome**, digite um nome descritivo para a política.
    
      - Para criar uma política de nível de site, clique em **Política de site**. No campo de pesquisa **Selecione um Site**, digite todo ou parte do nome do site para o qual deseja criar uma política. Na lista de sites, clique no site que deseja e em **OK**.
        
        <div>
        

        > [!NOTE]  
        > O nome do site se tornará o nome da política de conferências e não poderá ser alterado.

        
        </div>

5.  Em **Descrição**, digite uma descrição para a política.

6.  Sob **Política do Organizador**, em **Tamanho máximo de reuniões**, digite o número máximo de usuários que deseja permitir em uma reunião. Por padrão, o tamanho máximo de reuniões é 250.

7.  Para impedir que usuários convidem usuários anônimos para a reunião, desmarque a caixa de seleção **Permitir que participantes convidem usuários anônimos**. Usuários anônimos são usuários que não possuem credenciais nos serviços de domínio do Active Directory da sua organização e que, portanto, não são autenticados. Por padrão, os usuários podem convidar usuários anônimos para as reuniões.

8.  Em **Gravação**, execute um dos seguintes procedimentos:
    
      - Para evitar que os participantes gravem reuniões, clique em **Nenhum**. Esta é a configuração padrão.
    
      - Para permitir que os participantes gravem reuniões, clique em **Habilitar gravação**.

9.  Para permitir que os participantes externos gravem as reuniões, marque a caixa de seleção **Permitir que participantes anônimos e federados façam gravações**. O padrão é evitar que participantes externos gravem reuniões.

10. Em **Áudio/vídeo**, execute um dos seguintes procedimentos:
    
      - Para impedir o uso de áudio e vídeo, clique em **Nenhum**.
    
      - Para permitir o uso de áudio, mas não de vídeo, clique em **Habilitar áudio IP**.
    
      - Para permitir o uso de áudio e vídeo, clique em **Habilitar áudio/vídeo IP**. Esta é a configuração padrão.

11. Se você escolher permitir o uso de áudio em **Áudio/vídeo**, faça o seguinte:
    
      - Para impedir que usuários participem da reunião de forma discada, desmarque a caixa de seleção **Habilitar conferência discada PSTN**. Por padrão, os usuários podem participar de forma discada de reuniões usando PSTN.
    
      - Se você permitir que os usuários participem de forma discada das reuniões e deseja permitir que usuários não autenticados (anônimos) participem de uma reunião usando uma telefonia discada, marque a caixa de seleção **Permitir que participantes anônimos façam chamadas**. Com a telefonia discada, o servidor de conferência chama o usuário e o usuário atende ao telefone para participar da reunião. Por padrão, usuários anônimos não podem participar de uma reunião usando a telefonia discada.

12. Se você optar por permitir o uso de vídeo em **áudio/vídeo**, marque **permitir vários fluxos de vídeo** .

13. Em **Colaboração de dados**, execute um dos seguintes procedimentos:
    
      - Para impedir a colaboração de dados, clique em **Nenhum**.
    
      - Para permitir a colaboração de dados, clique em **Habilitar colaboração de dados**. Esta é a configuração padrão.

14. Se você escolher permitir a colaboração de dados em **Colaboração de dados**, faça o seguinte:
    
      - Para impedir os downloads externos, desmarque a caixa de seleção **Permitir que participantes anônimos e federados baixem conteúdo**. Por padrão, os usuários externos podem baixar conteúdo.
    
      - Para impedir as transferências de arquivo, desmarque a caixa de seleção **Permitir que participantes transfiram arquivos**. Por padrão, os usuários podem transferir arquivos.
    
      - Para impedir o uso de anotações, desmarque a caixa de seleção **Habilitar anotações**. Para o uso de anotações em fragmentar apresentações do PowerPoint, desmarque a **habilitar anotações do PowerPoint**. Por padrão, as anotações são permitidas.
    
      - Para impedir o uso de pools, desmarque a caixa de seleção **Habilitar pools**. Por padrão, os pools são permitidos.

15. Em **Compartilhamento de aplicativo**, execute um dos seguintes procedimentos:
    
      - Para impedir o uso do compartilhamento de aplicativos, clique em **Desabilitar o compartilhamento de aplicativos**.
    
      - Para permitir o uso do compartilhamento de aplicativos, clique em **Habilitar o compartilhamento de aplicativos**. Esta é a configuração padrão.

16. Se você escolher permitir o compartilhamento de aplicativos no **Compartilhamento de aplicativos**, faça o seguinte:
    
      - Para impedir que os participantes da reunião tomem o controle do compartilhamento de aplicativos, desmarque a caixa de seleção **Permitir que os participantes tomem o controle**. Por padrão, os participantes podem tomar o controle do compartilhamento de aplicativos.
    
      - Se você escolher permitir que os participantes da reunião tomem o controle do compartilhamento de arquivos, marque a caixa de seleção **Permitir que participantes federados e anônimos tomem o controle** para permitir que usuários externos tomem o controle do compartilhamento de aplicativos. Por padrão, os usuários externos não podem tomar controle do compartilhamento de aplicativos.

17. Em **Política do participante**, execute um dos seguintes procedimentos:
    
      - Para impedir o compartilhamento de aplicativos e o compartilhamento da área de trabalho, clique em **Desabilitar o compartilhamento de aplicativos e da área de trabalho**.
    
      - Para permitir o compartilhamento de aplicativos, mas não o compartilhamento da área de trabalho, clique em **Habilitar o compartilhamento de aplicativos**.
    
      - Para permitir o compartilhamento de aplicativos e da área de trabalho, clique em **Habilitar o compartilhamento de aplicativos e da área de trabalho**. Esta é a configuração padrão.

18. Para impedir as transferências de arquivo ponto a ponto, desmarque a caixa de seleção **Habilitar a transferência de arquivo ponto a ponto**. Por padrão, as transferências de arquivo ponto a ponto são permitidas.

19. Para permitir a gravação ponto a ponto, marque a caixa de seleção **Habilitar a gravação ponto a ponto**. Por padrão, a gravação ponto a ponto não é permitida.

20. Para permitir que os participantes ingressem com vários fluxos de vídeo, marque a caixa de seleção **permitir que os participantes ingressem com vários fluxos de vídeo** . Por padrão, vários fluxos de vídeo são permitidos.

21. Clique em **Confirmar**.

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a>Para modificar uma política de usuário ou de site existente

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Conferência** e em **Política de Conferência**.

4.  Na lista de políticas de conferência, clique na política que deseja alterar, clique em **Editar**e em **Mostrar detalhes**.

5.  Em **Editar Política de Conferências**, modifique qualquer uma das configurações de política, exceto seu nome, que não pode ser modificado.

6.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

