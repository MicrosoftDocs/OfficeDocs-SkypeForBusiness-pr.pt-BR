---
title: Personalizar propriedades de conta de usuário para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Você pode usar os procedimentos neste seção para modificar as propriedades de conta de usuários individuais.
ms.openlocfilehash: 6f2c3a76f9047da0a5d78695518cfb8355ab82e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826261"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Personalizar propriedades de conta de usuário para o Skype for Business Server
 
Você pode usar os procedimentos neste seção para modificar as propriedades de conta de usuários individuais.
  
Há duas operações básicas que podem ser feitas no nível do usuário individual:
  
- [Configurar opções de telefonia para uma conta de usuário específica](customize-properties.md#Tel_Op)
    
- [Mover usuários para outro pool](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Configurar opções de telefonia para uma conta de usuário específica
<a name="Tel_Op"> </a>

Você pode personalizar as configurações de telefonia para um usuário específico (desde que o usuário individual tenha sido habilitado para o Skype for Business Server e a organização suporte telefonia).
  
As opções de telefonia do usuário do Skype for Business Server incluem o seguinte:
  
- **Áudio/vídeo desabilitado** O usuário não pode fazer chamadas com áudio e vídeo.
    
- **Somente pc-pc** O usuário só pode fazer chamadas de áudio ou vídeo pc-PC.
    
- **Enterprise Voice** O usuário pode usar a infraestrutura do Skype for Business Server para rotear todas as chamadas de entrada e saída. O usuário também pode fazer chamadas PC-PC.
    
- **Controle de chamada remota** O usuário pode usar o Skype for Business Server para controlar o telefone de mesa e também pode fazer chamadas PC-PC.
    
Para obter detalhes sobre como configurar a telefonia para uma organização, consulte [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and Deploy Enterprise Voice in Skype for Business [Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.
  
1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários**, digite toda ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta que deseja e clique em **Localizar**.
    
5. Na tabela, clique na conta de usuário que deseja modificar.
    
6. No menu **Editar**, clique em **Modificar**.
    
7. Em **Telefonia**, faça o seguinte:
    
   - Para desabilitar as chamadas de áudio e vídeo do usuário, clique em   **Áudio/vídeo desabilitado**.
    
   - Para habilitar a comunicação de áudio PC-PC do usuário, mas não o controle de chamada remota ou o Enterprise Voice, clique em **Somente PC-PC**. Especifique um valor para **URI da Linha** para o telefone que o usuário usa para comunicações de áudio PC-PC.
    
   - Para rotear as chamadas telefônicas do usuário usando a infraestrutura do Skype for Business de acordo com a classe de política de serviço, incluindo a comunicação de áudio PC-PC, clique em **Enterprise Voice**. Em   **URI da Linha**, especifique o número de telefone para Enterprise Voice. Em **Política de plano de discagem** e **Política de Voz**, especifique as políticas apropriadas para o usuário. Para especificar as regras de normalização para conversão de números de telefone discados pelo usuário no formato E.164, selecione o perfil de local apropriado no em **Política de local**.
    
   - Para habilitar o controle de chamada remota, que permite que os usuários controlem sua linha de telefone de mesa do Skype for Business Server para fazer chamadas pc-to-PC e chamadas pc-para-telefone, clique em Controle de chamada **remota.** Em **URI da Linha**, especifique o número de telefone para o controle de chamada remota. O usuário deve ter um telefone de mesa e a conexão PBX (central privada de comutação telefônica) para roteamento de chamada.
    
## <a name="move-users-to-another-pool"></a>Mover usuários para outro pool
<a name="Move_Users"> </a>

Você pode usar o Painel de Controle do Skype for Business Server para atribuir usuários a um servidor ou pool específico.
  
> [!TIP]
> Mover todos os usuários existentes de um pool de origem que está executando o Lync Server 2010 ou anterior para um pool de destino do Skype for Business Server em um ambiente complexo do Active Directory pode resultar em replicação mais lenta do Active Directory. Para evitar isso, você pode usar filtros de pesquisa para mover usuários de pools que executam o Lync Server 2010 ou anterior separadamente, ou pode usar o Shell de Gerenciamento do Skype for Business Server para mover usuários com cmdlets. Além disso, a funcionalidade de filtro funciona com usuários do Skype for Business Server. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Para mover os usuários selecionados para um outro servidor ou pool

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.  
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome de conta do SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) da linha da conta de usuário que você deseja e clique em **Localizar**. 
    
5. Na tabela, selecione um usuário específico ou usuários na lista. 
    
6. No menu **Ação**, clique em **Mover usuários selecionados para o pool**.
    
7. Em **Mover Usuários**, selecione o pool para o qual você deseja mover os usuários em **Pool de registradores de destino**.
    
8. (Opcional) Se o pool ou o servidor de destino não estiver disponível, marque a caixa de seleção **Forçar**.
    
    > [!CAUTION]
    > Se você selecionar **Forçar**, a conta de usuário será movida, mas nenhum dado de usuário associado será excluído (por exemplo, conferências agendadas pelo usuário). Se essa opção não for selecionada, a conta e os dados associados serão movidos. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Para mover todos os usuários de um servidor ou pool para outro servidor ou pool

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.  
    
3. Na barra de navegação à esquerda, clique em **Usuários**.
    
4. No menu **Ação**, clique em **Mover todos os usuários para o pool**.
    
5. Em **Mover Usuários**, selecione o pool que contenha as contas de usuário que você deseja mover no **Pool de registradores de origem**.
    
6. Em **Pool de registradores de destino**, selecione o pool para o qual você deseja mover os usuários.
    
7. (Opcional) Se o pool ou o servidor de destino não estiver disponível, marque a caixa de seleção **Forçar**.
    
    > [!CAUTION]
    > Se você selecionar **Forçar**, a conta de usuário será movida, mas nenhum dado de usuário associado será excluído (por exemplo, conferências agendadas pelo usuário). Se essa opção não for selecionada, a conta e os dados associados serão movidos. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Para mover usuários de um pool para um pool diferente usando um filtro

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 
    
3. Na barra de navegação à esquerda, clique em **Usuários**.
    
4. Na **Pesquisa de Usuário,** clique **em Pesquisar** e em **Adicionar Filtro.**
    
5. Nos Critérios de pesquisa, selecione **Pool de Registradores**, selecione **Igual a**, selecione **FQDN Atual do Pool** e clique em **Localizar**.
    
6. No menu **Ação**, clique em **Mover todos os usuários para o pool**.
    
    > [!NOTE]
    > Quando um filtro é aplicado a um conjunto de usuário existente, a opção **Mover todos os usuários para o pool** está no contexto do subconjunto de usuários filtrados, não em **todos** os usuários possíveis.
  
7. Em **Mover Usuários**, selecione o pool que contenha as contas de usuário que você deseja mover no **Pool de registradores de origem**.
    
8. Em **Pool de registradores de destino**, selecione o pool para o qual você deseja mover os usuários.
    
9. (Opcional) Se o pool ou o servidor de destino não estiver disponível, marque a caixa de seleção **Forçar**.
    
    > [!CAUTION]
    > Se você selecionar **Forçar**, a conta de usuário será movida, mas nenhum dado de usuário associado será excluído (por exemplo, conferências agendadas pelo usuário e os contatos). Se essa opção não for selecionada, a conta e os dados associados serão movidos. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Para mover usuários de um pool para outro usando cmdlets do Windows Powershell

1. Dependendo de como você executar comandos do Windows PowerShell (ou seja, local ou remotamente), será necessário fazer logoff como membro das funções administrativas corretas do Skype for Business Server da seguinte maneira:
    
   a. Se você estiver executando os comandos na máquina local (por exemplo, faça logon diretamente em um Servidor Front-End): faça logon no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários,** conforme descrito em Delegate Setup Permissions .
    
   b. Se você estiver executando os comandos remotamente em outro computador (por exemplo, faça logon em seu computador e execute os comandos remotamente em um Servidor Front End Standard Edition): de uma conta de usuário atribuída à função CsUserAdministrator ou à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business** e no Shell de Gerenciamento do Skype for Business **Server.**
    
3. Para mover usuários único, use o cmdlet Move-CsUser da seguinte maneira:
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    Quando o usuário a ser movido for Pilar Ackerman, e for movido de seu pool doméstico atribuído atualmente para o pool pool01.contoso.net
    
4. Para mover muitos usuários, use os filtros com o cmdlet **Get-CsUser** e passe o conjunto resultante de usuários para **Move-CsUser**:
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    Os comandos combinados do **Get-CsUser** e do **Move-CsUser** devem resultar nisso:
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


