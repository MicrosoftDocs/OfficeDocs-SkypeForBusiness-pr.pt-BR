---
title: Personalizar propriedades da conta de usuário para Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Você pode usar os procedimentos nesta seção para modificar as propriedades de conta de usuário individual.
ms.openlocfilehash: 5162cb187538b5288f13f25beae96f3775faa594
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214832"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Personalizar propriedades da conta de usuário para Skype para Business Server
 
Você pode usar os procedimentos nesta seção para modificar as propriedades de conta de usuário individual.
  
Há duas operações básicas que podem ser feitas no nível do usuário individual:
  
- [Configurar opções de telefonia para uma conta de usuário específica](customize-properties.md#Tel_Op)
    
- [Mover usuários para outro pool](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Configurar opções de telefonia para uma conta de usuário específica
<a name="Tel_Op"> </a>

Você pode personalizar as configurações de telefonia para um usuário específico (desde que o usuário individual foi habilitado para Skype para Business Server e a organização dá suporte à telefonia).
  
Skype para opções de telefonia do usuário Business Server incluem o seguinte:
  
- **Áudio/vídeo desabilitado** O usuário não pode fazer chamadas com áudio e vídeo.
    
- **PC-PC somente** O usuário pode fazer somente PC-PC áudio ou vídeos chamadas.
    
- **Enterprise Voice** O usuário pode usar o Skype infra-estrutura de servidor de negócios para rotear todas as chamadas de entrada e saídas. O usuário também pode fazer chamadas de PC para PC.
    
- **Controle de chamada remota** O usuário pode usar o Skype para Business Server para controlar um telefone de mesa e também pode fazer chamadas de PC para PC.
    
Para obter detalhes sobre como configurar telefonia para uma organização, consulte [habilitar usuários para Enterprise Voice no Skype para Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) e [Implantar o Enterprise Voice no Skype para Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) na documentação de implantação.
  
1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários** , digite todo ou a primeira parte do nome para exibição, nome, sobrenome nome, nome de conta do Gerenciador de contas de segurança (SAM), endereço SIP ou linha identificador URI (Uniform Resource) da conta de usuário que você deseja e clique em **Find **.
    
5. Na tabela, clique na conta de usuário que você deseja modificar.
    
6. No menu **Editar** , clique em **Modificar**.
    
7. Em **telefonia**, faça o seguinte:
    
   - Para desabilitar as chamadas de áudio e vídeos para o usuário, clique em **áudio/vídeo desabilitado**.
    
   - Para habilitar as comunicações de áudio PC-PC do usuário, mas o controle de chamada remota não ou o Enterprise Voice, clique em **PC-PC apenas**. Especifica um valor para **URI de linha** de telefone que o usuário usa para comunicações de áudio PC-PC.
    
   - Para rotear chamadas de telefone do usuário usando o Skype para a infra-estrutura de negócios de acordo com a classe de política de serviço, incluindo a comunicação de áudio PC-PC, clique em **Enterprise Voice**. Em **URI da linha**, especifique o número de telefone para o Enterprise Voice. Na **política do plano de discagem** e **diretiva de voz**, especifique as políticas apropriadas para o usuário. Para especificar as regras de normalização para traduzir números de telefone discados pelo usuário para o formato e. 164, selecione o perfil de local apropriado na **política local**.
    
   - Para habilitar a chamada remota o controle, que permite aos usuários controlar sua linha de telefone de mesa do Skype para Business Server fazer chamadas de PC para PC e chamadas de PC para telefone, clique em **controle de chamada remota**. Em **URI da linha**, especifique o número de telefone para controle de chamada remota. O usuário deve ter um telefone de mesa e a conexão do privada de comutação telefônica (PBX) para roteamento de chamadas.
    
## <a name="move-users-to-another-pool"></a>Mover usuários para outro pool
<a name="Move_Users"> </a>

Você pode usar o Skype para painel de controle do Business Server para atribuir usuários a um servidor ou pool específico.
  
> [!TIP]
> Mover todos os usuários existentes de um pool de origem que está executando o Lync Server 2010 ou versão anterior para um Skype para pool de destino do servidor de negócios em um ambiente do Active Directory complexo pode resultar em mais lenta replicação do Active Directory. Para evitar isso, você pode usar filtros de pesquisa para mover usuários de pools que estejam executando o Lync Server 2010 ou anteriormente separadamente, ou você pode usar o Skype para Business Server Management Shell para mover usuários com cmdlets. Além disso, a funcionalidade do filtro funciona com o Skype para usuários corporativos Server. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Para mover usuários selecionados para um outro servidor ou pool

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários** , digite todo ou a primeira parte do nome para exibição, nome, sobrenome nome, nome de conta do Gerenciador de contas de segurança (SAM), endereço SIP ou linha identificador URI (Uniform Resource) da conta de usuário que você deseja e clique em **Find **. 
    
5. Na tabela, selecione um usuário específico ou usuários na lista. 
    
6. No menu **ação** , clique em **mover usuários selecionados para o pool**.
    
7. Em **Mover usuários**, selecione o pool que você deseja mover os usuários no **pool de registradores de destino**.
    
8. (Opcional) Se o servidor de destino ou o pool não estiver disponível, marque a caixa de seleção **Forçar** .
    
    > [!CAUTION]
    > Se você selecionar **Force**, a conta de usuário é movida, mas quaisquer dados de usuário associada são excluídos (por exemplo, conferências que o usuário tiver programado). Se você não selecionar a ele, a conta e os dados associados são movidos. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Para mover todos os usuários de um servidor ou pool para outro servidor ou pool

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. No menu **ação** , clique em **mover todos os usuários ao pool**.
    
5. Em **Mover usuários**, selecione o pool que contém as contas de usuário que você deseja mover no **pool de registradores de origem**.
    
6. Em **pool de registradores de destino**, selecione o pool que você deseja mover os usuários.
    
7. (Opcional) Se o servidor de destino ou o pool não estiver disponível, marque a caixa de seleção **Forçar** .
    
    > [!CAUTION]
    > Se você selecionar **Force**, a conta de usuário é movida, mas quaisquer dados de usuário associada são excluídos (por exemplo, conferências que o usuário tiver programado). Se você não selecionar a ele, a conta e os dados associados são movidos. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Para mover usuários de um pool para um pool diferente usando um filtro

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Em **Pesquisa de usuário**, clique em **Pesquisar**e, em seguida, clique em **Adicionar filtro**.
    
5. Nos critérios de pesquisa, selecione **Pool de registradores**, selecione é **igual a**, selecione **FQDN atual do Pool**e clique em **Localizar**.
    
6. No menu **ação** , clique em **mover todos os usuários ao pool**.
    
    > [!NOTE]
    > Quando um filtro é aplicado a um conjunto existente de usuários, a opção **mover todos os usuários para o pool** está no contexto do subconjunto de filtrada de usuários, não em **todos os** usuários possíveis.
  
7. Em **Mover usuários**, selecione o pool que contém as contas de usuário que você deseja mover no **pool de registradores de origem**.
    
8. Em **pool de registradores de destino**, selecione o pool de onde você deseja mover os usuários.
    
9. (Opcional) Se o servidor de destino ou o pool não estiver disponível, marque a caixa de seleção **Forçar** .
    
    > [!CAUTION]
    > Se você selecionar **Force**, a conta de usuário é movida, mas quaisquer dados de usuário associada são excluídos (por exemplo, conferências que o usuário tiver programado e contatos). Se você não selecionar a ele, a conta e os dados associados são movidos. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Para mover usuários de um pool para outro usando cmdlets do Windows Powershell

1. Dependendo de como você executa comandos do Windows PowerShell (ou seja, local ou remotamente), você precisa fazer logon como membro do Skype correto para funções administrativas do Business Server da seguinte maneira:
    
   a. Se você estiver executando os comandos na máquina local (por exemplo, você faça logon diretamente em um servidor Front-End): faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo RTCUniversalServerAdmins ou com o necessário direitos de usuário, conforme descrito em **Delegate Setup Permissions**.
    
   b. Se você estiver executando os comandos remotamente em outro computador (por exemplo, você faz logon seu computador e executa os comandos remotamente em um Standard Edition servidor Front-End): a partir de uma conta de usuário atribuída à função CsUserAdministrator ou a CsAdministrator função, faça logon em qualquer computador em sua implantação interna.
    
2. Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique **Skype para negócios**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**.
    
3. Para mover usuários únicos, use o cmdlet Move-CsUser conforme segue:
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    Onde o usuário mover é o usuário Pilar Ackerman e o usuário será movido de seu pool doméstico atribuído atualmente para o pool pool01. contoso.NET
    
4. Para mover um grande número de usuários, use os filtros com o cmdlet **Get-CsUser** e passe o conjunto resultante de usuários para **Move-CsUser**:
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    Os comandos combinados do **Get-CsUser** e **Move-CsUser** podem resultar nisto:
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


