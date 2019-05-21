---
title: Personalizar as propriedades da conta de usuário para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Você pode usar os procedimentos desta seção para modificar propriedades de conta de usuário individuais.
ms.openlocfilehash: d0e1a3ac02f5696e91e07c0f08cf0cf10e09f98e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275070"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Personalizar as propriedades da conta de usuário para o Skype for Business Server
 
Você pode usar os procedimentos desta seção para modificar propriedades de conta de usuário individuais.
  
Há duas operações básicas que podem ser realizadas no nível do usuário individual:
  
- [Configurar opções de telefonia para uma conta de usuário específica](customize-properties.md#Tel_Op)
    
- [Mover usuários para outro pool](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Configurar opções de telefonia para uma conta de usuário específica
<a name="Tel_Op"> </a>

Você pode personalizar as configurações de telefonia para um usuário específico (desde que o usuário individual tenha sido habilitado para o Skype for Business Server e a organização seja compatível com a telefonia).
  
As opções de telefonia do usuário do Skype for Business Server incluem o seguinte:
  
- **Áudio/vídeo desabilitado** O usuário não pode fazer chamadas com áudio e vídeo.
    
- **PC para PC somente** O usuário pode fazer apenas chamadas de áudio e com vídeo para PC para PC.
    
- **Enterprise Voice** O usuário pode usar a infraestrutura do Skype for Business Server para direcionar todas as chamadas de entrada e saída. O usuário também pode fazer chamadas de PC para PC.
    
- **Controle de chamada remota** O usuário pode usar o Skype for Business Server para controlar o telefone de mesa e também pode fazer chamadas de PC para PC.
    
Para obter detalhes sobre como configurar a telefonia de uma organização, consulte [habilitar usuários do Enterprise Voice no Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) e [implantar o Enterprise Voice no Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) na documentação de implantação.
  
1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam), endereço SIP ou URI (Uniform Resource Identifier) da conta de usuário que você deseja e clique em **Localizar **.
    
5. Na tabela, clique na conta de usuário que você deseja modificar.
    
6. No menu **Editar** , clique em **Modificar**.
    
7. Em **telefonia**, faça o seguinte:
    
   - Para desativar as chamadas de áudio e vídeo para o usuário, clique em **áudio/vídeo desabilitado**.
    
   - Para habilitar as comunicações de áudio PC para PC para o usuário, mas não o controle de chamada remota ou o Enterprise Voice, clique em **PC para PC somente**. Especifique um valor para o **URI da linha** para o telefone que o usuário usa para comunicações de áudio PC para PC.
    
   - Para encaminhar as chamadas telefônicas do usuário usando a infraestrutura do Skype for Business, de acordo com a classe de política de serviço, incluindo comunicação de áudio PC para PC, clique em **Enterprise Voice**. Em **URI da linha**, especifique o número de telefone do Enterprise Voice. Em **política de plano** de discagem e **política de voz**, especifique as políticas adequadas para o usuário. Para especificar as regras de normalização para a tradução de números de telefone discados pelo usuário para o formato E. 164, selecione o perfil de localização apropriado na **política de localização**.
    
   - Para habilitar o controle de chamada remota, que permite que os usuários controlem a linha de telefone da área de trabalho do Skype for Business Server para fazer chamadas de PC para PC e chamadas de PC para telefone, clique em **controle de chamada remota**. Em **URI de linha**, especifique o número de telefone para o controle de chamada remota. O usuário deve ter uma conexão de telefone de mesa e PBX (Private Branch Exchange) para roteamento de chamadas.
    
## <a name="move-users-to-another-pool"></a>Mover usuários para outro pool
<a name="Move_Users"> </a>

Você pode usar o painel de controle do Skype for Business Server para atribuir usuários a um servidor ou pool específico.
  
> [!TIP]
> Mover todos os usuários existentes de um pool de origem que esteja executando o Lync Server 2010 ou anterior para um pool de destino do Skype for Business Server em um ambiente do Active Directory complexo pode resultar em uma replicação mais lenta do Active Directory. Para evitar isso, você pode usar filtros de pesquisa para mover os usuários de pools que executam o Lync Server 2010 ou anterior separadamente, ou pode usar o Shell de gerenciamento do Skype for Business Server para mover usuários com cmdlets. Além disso, a funcionalidade de filtro funciona com usuários do Skype for Business Server. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Para mover os usuários selecionados para um servidor ou pool diferente

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.  
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam), endereço SIP ou URI (Uniform Resource Identifier) da conta de usuário que você deseja e clique em **Localizar **. 
    
5. Na tabela, selecione um usuário ou usuários específicos na lista. 
    
6. No menu **ação** , clique em **mover usuários selecionados para o pool**.
    
7. Em **mover usuários**, selecione o pool para o qual você deseja mover os usuários no **pool**de registradores de destino.
    
8. Adicionais Se o servidor ou o pool de destino não estiver disponível, marque a caixa de seleção **forçar** .
    
    > [!CAUTION]
    > Se você selecionar **forçar**, a conta do usuário será movida, mas todos os dados do usuário associados serão excluídos (por exemplo, conferências que o usuário agendou). Se você não selecioná-lo, a conta e os dados associados serão movidos. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Para mover todos os usuários de um servidor ou pool para um servidor ou pool diferente

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.  
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. No menu **ação** , clique em **mover todos os usuários para o pool**.
    
5. Em **mover usuários**, selecione o pool que contém as contas de usuário que você deseja mover no **pool**de registradores de origem.
    
6. No **pool**de registradores de destino, selecione o pool para o qual você deseja mover os usuários.
    
7. Adicionais Se o servidor ou o pool de destino não estiver disponível, marque a caixa de seleção **forçar** .
    
    > [!CAUTION]
    > Se você selecionar **forçar**, a conta do usuário será movida, mas todos os dados do usuário associados serão excluídos (por exemplo, conferências que o usuário agendou). Se você não selecioná-lo, a conta e os dados associados serão movidos. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Para mover os usuários de um pool para um pool diferente usando um filtro

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Em **pesquisa de usuário**, clique em **Pesquisar**e, em seguida, clique em **Adicionar filtro**.
    
5. Nos critérios de pesquisa, selecione **pool**de registradores, selecione **igual a**, selecione o **FQDN do pool atual**e clique em **Localizar**.
    
6. No menu **ação** , clique em **mover todos os usuários para o pool**.
    
    > [!NOTE]
    > Quando um filtro é aplicado a um conjunto de usuários existente, a opção **mover todos os usuários para o pool** está no contexto do subconjunto filtrado de usuários, e não **todos** os usuários possíveis.
  
7. Em **mover usuários**, selecione o pool que contém as contas de usuário que você deseja mover no **pool**de registradores de origem.
    
8. No **pool**de registradores de destino, selecione o pool para o qual você deseja mover os usuários.
    
9. Adicionais Se o servidor ou o pool de destino não estiver disponível, marque a caixa de seleção **forçar** .
    
    > [!CAUTION]
    > Se você selecionar **forçar**, a conta do usuário será movida, mas todos os dados do usuário associados serão excluídos (por exemplo, conferências que o usuário agendou e os contatos). Se você não selecioná-lo, a conta e os dados associados serão movidos. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Para mover os usuários de um pool para outro usando cmdlets do Windows PowerShell

1. Dependendo de como você executa comandos do Windows PowerShell (ou seja, local ou remotamente), você precisa fazer logon como membro das funções administrativas corretas do Skype for Business Server da seguinte forma:
    
   a. Se você estiver executando os comandos no computador local (por exemplo, você fizer logon diretamente em um servidor front-end): faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com o necessário direitos de usuário, conforme descrito em **permissões de configuração de representante**.
    
   b. Se você estiver executando os comandos remotamente em outro computador (por exemplo, se conectar ao seu computador e executar os comandos remotamente em um servidor front-end Standard Edition): de uma conta de usuário atribuída à função CsUserAdministrator ou ao CsAdministrator , faça logon em qualquer computador na sua implantação interna.
    
2. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.
    
3. Para mover usuários únicos, use o cmdlet Move-CsUser da seguinte maneira:
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    Onde o usuário mover é o usuário pilar Alverca, e o usuário será movido do pool inicial atribuído no momento para o pool pool01.contoso.net
    
4. Para mover um grande número de usuários, use filtros com o cmdlet **Get-CsUser** e passe o conjunto resultante de usuários para **mover-CsUser**:
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    Os comandos combinados do **Get-CsUser** e do **move-CsUser** podem fazer isso:
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


