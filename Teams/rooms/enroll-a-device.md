---
title: Registrar um dispositivo de Sala do Teams nos Serviços Gerenciados
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 07/22/2022
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Integração Salas do Teams dispositivos a serviços gerenciados
f1keywords: ''
ms.openlocfilehash: 07fbb2b196c0f74b34dbe2018865181e57aca17b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272036"
---
# <a name="enroll-device-into-managed-service"></a>Registrar dispositivo no Serviço Gerenciado

A implantação requer integração Salas do Microsoft Teams dispositivos aos Salas do Microsoft Teams gerenciados. O agente de serviço de monitoramento é para uso com sistemas e periféricos certificados da MTR (Sala do Microsoft Teams).

## <a name="prerequisites"></a>Pré-requisitos

Siga estes procedimentos para configurar o hardware antes de tentar o processo de registro:

### <a name="adding-proxy-settings-optional"></a>Adicionando configurações de proxy (opcional)

1. Faça logon como administrador seguindo [a execução de operações Administração usuário do dispositivo MTR](#performing-operations-as-the-admin-user-of-the-mtr-device).
1. No campo ***Pesquisar** _ do Windows (seção inferior esquerda da tela), insira _ *cmd** (pressione a tela ou selecione para a direita e escolha Executar **_como administrador_**).
1. Execute o seguinte comando (aspas duplas no final do comando são importantes):

   - Se estiver usando um ***único servidor proxy***: `bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY <proxyserver>:<port> ""`

     *Exemplo:*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY contosoproxy.corp.net:8080 ""
     ```

   - Se estiver usando um ***arquivo pac*** : `bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url>`

     *Exemplo:*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT `http://contosoproxy.corp.net/proxy.pac`
     ```

### <a name="enabling-tpm-settings"></a>Habilitando as configurações do TPM

> [!NOTE]
> O TPM deve ser habilitado para se registrar no serviço gerenciado.

Se o TPM em um dispositivo Intel NUC estiver desabilitado, habilite o TPM nesses dispositivos da seguinte maneira:

1. Conecte o teclado a um dispositivo NUC.
1. Reinicie o dispositivo.
1. Para exibir a tela do BIOS, pressione **F2 rapidamente**.
1. Selecione **Avançado**.
1. Selecione **Segurança**.
1. No lado direito, abaixo dos Recursos de Segurança, habilite a **Tecnologia de Confiança da Plataforma Intel**.
1. Para salvar suas configurações, pressione **F10**.
1. Na caixa de confirmação, selecione **Sim**.

## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>Executando operações como Administração usuário do dispositivo MTR

Alguns procedimentos de configuração/instalação exigem que você faça logon no dispositivo como Administrador.

Para fazer logon no dispositivo como Administrador (administrador local):

1. Certifique-se de desligar todas as chamadas em andamento e retornar à tela inicial.
1. Na interface do usuário da Sala do Microsoft Teams, selecione Mais e, em **seguida, selecione** Configurações, em que você será solicitado a fornecer a senha de Administrador local no dispositivo (a senha padrão é **_sfb_**).
1. Selecione **Configurações e**, em seguida,  **selecione Configurações do Windows**  para acessar o Windows como administrador local.

1. Na lista de usuários exibida na tela de logon do Windows, selecione  **Administrador** (ou o respectivo administrador local do seu dispositivo).

> [!NOTE]
> Se o *computador estiver* ingressado no domínio, escolha Outro **Usuário e use** **.\admin** ou o nome de usuário do administrador local configurado no dispositivo como o nome de usuário.

Para retornar ao aplicativo Salas do Microsoft Teams depois de executar as tarefas administrativas necessárias:

1. No ***menu Iniciar do*** Windows, saia da conta Administração usuário.
1. Retorne ao Salas do Microsoft Teams selecionando o ícone da conta de usuário no lado esquerdo da tela e, em seguida, selecionando **o Skype**.

> [!NOTE]
> Se o usuário do Skype não estiver listado, selecione Outro Usuário, insira ***.\skype*** como o nome de usuário e entre.

## <a name="urls-required-for-communication"></a>URLs necessárias para comunicação

 > [!NOTE]
 > Todo o tráfego de rede entre o agente de dispositivos MTR e o portal do serviço Salas do Microsoft Teams – Serviços Gerenciados é SSL pela porta 443 *.*  Consulte [Office 365 URLs e intervalos de endereços IP - Microsoft 365 Enterprise | Microsoft Docs](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

Os hosts a seguir devem ser permitidos se você tiver a **lista de permissões de tráfego** habilitada em seu ambiente corporativo:

agent.rooms.microsoft.com<br>
global.azure-devices-provisioning.net<br>
gj3ftstorage.blob.core.windows.net<br>
mmrstgnoamiot.azure-devices.net<br>
mmrstgnoamstor.blob.core.windows.net<br>
mmrprodapaciot.azure-devices.net<br>
mmrprodapacstor.blob.core.windows.net<br>
mmrprodemeaiot.azure-devices.net<br>
mmrprodemeastor.blob.core.windows.net<br>
mmrprodnoamiot.azure-devices.net<br>
mmrprodnoamstor.blob.core.windows.net

## <a name="enrollment-process"></a>Processo de registro

O processo de registro envolve estas etapas:

1. Na barra de navegação à esquerda do portal [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/)Salas do Microsoft Teams – Serviços Gerenciados, expanda **Configurações** e selecione **Geral**.
1. Em *Registrar uma sala*, selecione **Baixar instalador**  para baixar o software do agente de monitoramento.
1. **Opcional:** Definir configurações de proxy para o agente; consulte [Adicionando configurações de proxy (opcional)](#adding-proxy-settings-optional).
1. Instale o instalador do agente (baixado na etapa 2) em unidades MTR, executando o MSI localmente em um dispositivo MTR ou por meio de seus meios normais de publicar aplicativos MSI em massa em dispositivos em seu ambiente (Política de Grupo etc.)
1. A sala aparece no portal dentro de 5 a 10 minutos. Caso contrário, entre em contato com managedroomsupport@microsoft.com.

   ![Captura de tela das configurações e das chaves de registro automático.](../media/software-installation-005new.png)

> [!NOTE]
> Se você precisar instalar o agente sem que o aplicativo Teams no MTR possa fazer logon no Teams, poderá usar nossa chave de registro como um processo opcional. Ir para '?'  (Ajuda) no canto superior direito do portal e selecione "Chave de download (opcional)". Ao instalar o agente, coloque a 'chave de auto-registro' (baixada anteriormente do portal) no diretório **C:\Rigel** do dispositivo.

## <a name="installation"></a>Instalação

Depois de baixar o instalador da Microsoft (no portal ou usando a URL AKA.ms fornecida acima), descompacte seu conteúdo para acessar o arquivo **ManagedRoomsInstaller.msi.**

Há dois modos de instalação: 1) instalação de computador local individual e 2) modo de implantação em massa (geralmente por meio Intune de método semelhante). Recomendamos a instalação individual para computadores que não ingressaram no domínio ou para computadores que você não tem como executar instaladores MSI remotamente.

Devido às várias maneiras variadas em que os clientes podem executar aplicativos MSI no modo de implantação em massa, este documento percorre apenas a instalação no modo individual, bem como em massa em Intune registrados em massa.

### <a name="individual-device-installation"></a>Instalação de dispositivo individual

1. Faça logon no dispositivo como administrador. Verifique se *as operações de execução como Administração usuário das etapas do* dispositivo são seguidas.

1. Copie o arquivo **ManagedRoomsInstaller.msi** para o dispositivo MTR.

   Ao ***executar oManagedRoomsInstaller.msi*** é uma tela do Contrato de Licença.

1. Depois de ler o contrato, marque ***Aceito os termos** no Contrato de Licença_ e pressione _*Instalar**.

    Isso inicia a instalação do Salas do Microsoft Teams – Software de monitoramento dos Serviços Gerenciados. Um prompt de elevação (executar como administrador) é exibido.

1. Selecione **Sim**.

    A instalação continuará. Durante o procedimento de instalação, uma janela do console é aberta e inicia o estágio final da instalação do software de monitoramento Salas do Microsoft Teams – Serviços Gerenciados.

    > [!NOTE]
    > Não feche a janela. Depois que a instalação for concluída, o assistente exibirá um botão "Concluir".

### <a name="intune-enrolled-device-bulk-deployment"></a>Intune em massa do dispositivo registrado

Os seguintes componentes são pré-requisitos para a instalação bem-sucedida: 

- **Intune registro**: Salas do Teams em dispositivos Windows já deve estar registrado no Intune.
  Para obter mais informações sobre como registrar o Salas do Teams em dispositivos Windows no Intune, consulte Registrar o Salas do Microsoft Teams em dispositivos Windows com o [Microsoft Endpoint Manager – Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- **Azure AD** grupo com todos os Salas do Teams em dispositivos Windows como membros – um grupo criado no Azure AD que inclui todos os Salas do Teams em dispositivos Windows que devem fazer parte do serviço Salas do Microsoft Teams Premium. Esse grupo será usado para direcionar a implantação do agente MTRP.
  
> [!NOTE]
> Você pode considerar o uso de grupos dinâmicos no Azure AD para essa finalidade, mais informações sobre como registrar o Salas do Microsoft Teams em dispositivos Windows com o [Microsoft Endpoint Manager – Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- **Baixar o instalador do agente MTRP** **– baixe** o arquivo zip <https://aka.ms/serviceportalagentmsi> do agente e extraia o conteúdo do zip (ManagedRoomsInstaller.msi) para uma pasta temporária local.

**Para instalar usando Intune**

1. Entre no Centro [de administração do Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)
1. Selecione **Aplicativos Adicionados** > **a Todos os** > **Aplicativos**.
1. No painel **Selecionar tipo de** aplicativo, em **Outros** tipos de aplicativo, selecione **Aplicativo de Linha de Negócios**.
1. Clique **em Selecionar**. As **etapas adicionar** aplicativo são exibidas. 
1. No painel **Adicionar aplicativo** , clique em **Selecionar arquivo de pacote do aplicativo**.
   1. No painel **arquivo do pacote de** aplicativos, selecione  **Procurar**. Em seguida, selecione **ManagedRoomsInstaller.msi** arquivo baixado anteriormente (consulte a seção de pré-requisitos).
   1. Quando terminar, selecione **OK** no painel arquivo **do** pacote do aplicativo para adicionar o aplicativo.
1. Na página **Informações do** aplicativo, execute as seguintes alterações:
   1. Publicador: insira **a Microsoft Corporation**.
   1. Ignorar versão do aplicativo: selecione **Sim**.

      > [!NOTE]
      > O agente MTRP está se atualizando; portanto, você deve ignorar explicitamente a versão do aplicativo (qualquer versão de linha de base pode ser atualizada automaticamente).

   1. (Opcional) Categoria: Selecione Gerenciamento **do Computador**.
   
1. Clique **em Avançar** para exibir **a página Atribuições** .
   1. Na seção **Obrigatório, clique** em **+ adicionar grupo para** direcionar um grupo de dispositivos para a instalação do agente.
   1. No painel **Selecionar grupo**, digite o nome do grupo na caixa Pesquisar (consulte os pré-requisitos acima) e clique no grupo desejado e clique em  **Selecionar**.
      Para obter mais informações, consulte [Adicionar grupos para organizar usuários e dispositivos](https://go.microsoft.com/fwlink/?linkid=2202166) e [atribuir aplicativos a grupos com Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2202270).
1. Clique **em Avançar** para exibir **a página Examinar +** criar.
1. Examine os valores e as configurações que você inseriu para o aplicativo. Quando terminar, clique em **Criar** para adicionar o aplicativo Intune.

Depois que o processo for concluído, seus dispositivos começarão a instalar o agente MTRP após alguns minutos.

> [!NOTE]
> Após a instalação, o agente MTRP pode levar até oito horas para executar uma atualização automática para a versão mais recente e ser listado no portal do MTRP.
Para agilizar o registro automático no portal do MTRP, considere reiniciar o dispositivo MTR após a implantação do agente.

## <a name="completing-enrollment"></a>Concluindo o registro

Quando a instalação for concluída, aguarde de 5 a 10 minutos e, em seguida, atualize o portal para exibir o dispositivo na lista, relatado como estado *de* integração.

No *estado de* integração, o status da sala é exibido e atualizado, mas não gera alertas nem cria tíquetes de investigação.

Escolha a sala e selecione **Registrar para**  começar a receber alertas de incidentes, tíquetes de investigação ou para relatar um incidente.

Para dúvidas ou problemas, abra um incidente relatado pelo cliente no portal ou entre em contato com managedroomsupport@microsoft.com.

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>Cancelar o registro e desinstalar o software de monitoramento

Para cancelar o registro do dispositivo, remova o agente de monitoramento do dispositivo MTR da seguinte maneira:

1. No dispositivo que está sendo monitorado, faça logon no dispositivo como administrador. Siga as etapas na execução de operações *como o Administração usuário do dispositivo*.
1. Baixe o script de redefinição [aka.ms/MTRPDeviceOffBoarding](https://aka.ms/MTRPDeviceOffBoarding).
1. Extraia o script em algum lugar no dispositivo e copie o caminho.
1. Abra o PowerShell como administrador: no campo ***Pesquisar** _ do Windows (seção inferior esquerda da tela), insira 'Powershell' e clique com o botão direito do mouse em _*_Windows PowerShell_**.
1. Selecione *"Executar como Administrador"* e aceite o prompt do UAC.
1. Insira *Set-ExecutionPolicy –ExecutionPolicy RemoteSigned* e pressione **Y** no próximo prompt.
1. Cole ou digite o caminho completo para o script de remoção descompactado na janela do PowerShell e pressione **Enter**.

   Exemplo:

   ```powershell
   C:\Users\admin\Downloads\MTRP\_Device\_Offboarding\MTRP\_Device\_Offboarding.ps1
   ```

   Esse comando redefine o dispositivo para atualizações de MTR padrão do usuário e remove o agente de monitoramento e os arquivos do MTRP.

1. No menu à esquerda no portal Salas do Microsoft Teams – Serviços Gerenciados, selecione **Salas**.
1. Na lista de salas fornecidas, escolha a sala que você deseja cancelar o registro e selecione Cancelar  registro para parar de receber alertas de incidentes ou tíquetes de investigação ou para relatar um incidente para a sala.

## <a name="troubleshooting-table"></a>Tabela de solução de problemas

> [!NOTE]
> Todos Salas do Microsoft Teams – Os erros de monitoramento dos Serviços Gerenciados são registrados em um arquivo específico do Log de Eventos chamado Salas **Gerenciadas da Microsoft**.

***Local do arquivo de log do runtime do aplicativo*** =

C:\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x.x\ServicePortalAgent\ServicePortal\_Verbose\_LogFile.log, em que **x.x.x** é o número de versão do aplicativo.

|Sintoma|Procedimento recomendado|
|---|---|
|Você recebe uma mensagem de erro informando: </p><p> ***ERRO: Execute este aplicativo com_** <br> Privilégios *__elevated_**|Execute o aplicativo com privilégios escalonados e tente novamente.|
|||
|Você recebe uma mensagem de erro informando: </p><p> ***Dados do TPM não podem ser encontrados***|Verifique se o dispositivo tem o TPM (Trusted Platform Module) ativado em seu BIOS. Isso geralmente é encontrado nas configurações de segurança do BIOS do dispositivo.|
|||
|Você recebe uma mensagem de erro: </p><p> ***ERRO: Conta de usuário local chamada 'Administração' ou 'Skype' não encontrada***|Verifique se as contas de usuário existem no dispositivo certificado de sistemas da Sala do Microsoft Teams.|
|||
|Você recebe todas as mensagens de estado de erro que não são abordadas acima.|Forneça uma cópia do log de instalação para o agente de suporte do Microsoft Teams System.|
