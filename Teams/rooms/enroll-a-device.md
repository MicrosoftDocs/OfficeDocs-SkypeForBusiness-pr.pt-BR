---
title: Registrar um dispositivo do Teams Room no Pro Management
author: altsou
ms.author: altsou
manager: serdars
ms.date: 09/28/2022
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
description: Integrando dispositivos Salas do Teams ao portal do Pro Management
f1keywords: ''
ms.openlocfilehash: f5994c5ced6097104ee74044ee2441bc8388f5c3
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307956"
---
# <a name="enroll-device-into-pro-management"></a>Registrar dispositivo no Pro Management

A implantação requer a integração de dispositivos Salas do Microsoft Teams ao portal de Gerenciamento de Salas Microsoft Teams Pro. O agente de serviço de monitoramento é usado com sistemas MTR (Microsoft Teams Room) certificados e periféricos.

## <a name="prerequisites"></a>Pré-requisitos

Siga estes procedimentos para configurar seu hardware antes de tentar o processo de registro:

### <a name="adding-proxy-settings-optional"></a>Adicionar configurações de proxy (opcional)

1. Faça logon como administrador [seguindo a execução de operações como o Administração usuário do dispositivo MTR](#performing-operations-as-the-admin-user-of-the-mtr-device).
1. No campo Windows ***Search** _ (seção inferior esquerda da tela), insira _ *cmd** (pressione longamente a tela ou selecione à direita e escolha **_Executar como administrador_**).
1. Execute o seguinte comando (aspas duplas no final do comando são importantes):

   - Se estiver usando ***um único servidor proxy***: `bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY <proxyserver>:<port> ""`

     *Exemplo:*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY contosoproxy.corp.net:8080 ""
     ```

   - Se estiver usando um arquivo ***pac*** : `bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url>`

     *Exemplo:*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT http://contosoproxy.corp.net/proxy.pac
     ```

### <a name="enabling-tpm-settings"></a>Habilitando configurações de TPM

> [!NOTE]
> O TPM deve estar habilitado para se inscrever no Pro Management.

Se o TPM em um dispositivo Intel NUC estiver desabilitado, habilite o TPM nesses dispositivos da seguinte maneira:

1. Conecte o teclado a um dispositivo NUC.
1. Reinicie o dispositivo.
1. Para exibir a tela BIOS, pressione **rapidamente F2**.
1. Selecione **Avançado**.
1. Selecione **Segurança**.
1. No lado direito abaixo dos Recursos de Segurança, habilite a **Tecnologia de Confiança da Plataforma Intel**.
1. Para salvar suas configurações, pressione **F10**.
1. Na caixa de confirmação, selecione **Sim**.

## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>Executando operações como o usuário Administração do dispositivo MTR

Alguns procedimentos de configuração/instalação exigem que você faça logon no dispositivo como Administrador.

Para fazer logon no dispositivo como Administrador (administrador local):

1. Certifique-se de desligar as chamadas em andamento e retornar à tela inicial.
1. Na interface do usuário Microsoft Teams Room, selecione **Mais** e, em seguida, selecione **Configurações**, em que você é solicitado para a senha do administrador local no dispositivo (a senha padrão é **_sfb_**).
1. Selecione **Configurações** e selecione  **Configurações do Windows**  para acessar o Windows como administrador local.

1. Na lista de usuários exibidos na tela de logon do Windows, selecione  **Administrador** (ou o respectivo administrador local do dispositivo).

> [!NOTE]
> Se o computador for *ingressado no domínio*, escolha **Outro Usuário** e use **.\admin** ou o nome de usuário do administrador local configurado no dispositivo como o nome de usuário.

Para retornar ao aplicativo Salas do Microsoft Teams depois de executar as tarefas administrativas necessárias:

1. No ***menu Iniciar*** do Windows, saia da conta Administração.
1. Retorne ao Salas do Microsoft Teams selecionando o ícone da conta de usuário no lado esquerdo da tela e selecionando o **Skype**.

> [!NOTE]
> Se o usuário do Skype não estiver listado, selecione Outro Usuário e ***insira .\skype*** como o nome de usuário e entre.

## <a name="urls-required-for-communication"></a>URLs necessárias para comunicação

 > [!NOTE]
 > Todo o tráfego de rede entre o agente de dispositivos MTR e o portal de Gerenciamento de Salas Microsoft Teams Pro é SSL pela porta 443 *.*  Consulte [URLs Office 365 e intervalos de endereços IP – Microsoft 365 Enterprise | Microsoft Docs](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

Os seguintes hosts devem ser permitidos se você tiver **a lista de permissões de tráfego** habilitada em seu ambiente corporativo:

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

1. Na barra de navegação à esquerda do portal [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/)de Gerenciamento de Salas Microsoft Teams Pro , expanda **Configurações** e selecione **Geral**.
1. Em *Registrar uma sala*, selecione **Baixar instalador**  para baixar o software do agente de monitoramento.
1. **Opcional:** Configurar configurações de proxy para o agente; consulte [Adicionar configurações de proxy (opcional)](#adding-proxy-settings-optional).
1. Instale o instalador do agente (baixado na etapa 2) em unidades MTR, executando o MSI localmente em um dispositivo MTR ou por meio de seus meios normais de publicar aplicativos MSI em massa em dispositivos em seu ambiente (Group-Policy etc.)
1. A sala é exibida no portal dentro de 5 a 10 minutos.

   ![Captura de tela das configurações e das chaves de auto-registro.](../media/software-installation-005new.png)

> [!NOTE]
> Se você precisar instalar o agente sem que o Aplicativo teams no MTR possa fazer logon no Teams, use nossa chave de registro como um processo opcional. Vá para '?'  (Ajuda) no canto superior direito do portal e selecione 'Baixar chave (opcional)'. Ao instalar o agente, coloque a 'chave de auto-registro' (baixada anteriormente do portal) no diretório **C:\Rigel** do dispositivo.

## <a name="installation"></a>Instalação

Depois de baixar o instalador de Microsoft (no portal ou usando a URL AKA.ms fornecida acima), descompacte seu conteúdo para acessar o arquivo **ManagedRoomsInstaller.msi**.

Há dois modos de instalação: 1) instalação de máquina local individual e 2) modo de implantação em massa (geralmente por meio de Intune de método semelhante). Recomendamos a instalação individual para máquinas ingressadas fora do domínio ou para computadores que você não tem como executar instaladores MSI remotamente.

Devido às várias maneiras pelas quais os clientes podem executar aplicativos MSI no modo de implantação em massa, este documento percorre apenas a instalação no modo individual, bem como em massa em dispositivos registrados em Intune.

### <a name="individual-device-installation"></a>Instalação de dispositivo individual

1. Faça logon no dispositivo como administrador. Verifique se as *operações de execução como o Administração usuário das etapas do dispositivo* são seguidas.

1. Copie o **arquivoManagedRoomsInstaller.msi** para o dispositivo MTR.

   Ao executar o ***ManagedRoomsInstaller.msi*** é uma tela contrato de licença.

1. Depois de ler o contrato, verifique ***Aceito os termos no Contrato de Licença** _ e pressione _*Install**.

    Isso inicia a instalação do software de monitoramento Salas Microsoft Teams Pro. Um prompt para elevação (executar como administrador) é exibido.

1. Selecione **Sim**.

    A instalação continuará. Durante o procedimento de instalação, uma janela do console abre e inicia o estágio final da instalação do software de monitoramento Salas Microsoft Teams Pro.

    > [!NOTE]
    > Não feche a janela. Depois que a instalação for concluída, o assistente exibirá um botão "Concluir".

### <a name="intune-enrolled-device-bulk-deployment"></a>Implantação em massa de dispositivo registrada Intune

Os seguintes componentes são pré-requisitos para a instalação bem-sucedida: 

- **Intune registro**: Salas do Teams em dispositivos Windows já devem estar registrados no Intune.
  Para obter mais informações sobre como registrar Salas do Teams em dispositivos Windows em Intune, consulte [Registrar Salas do Microsoft Teams em dispositivos Windows com Microsoft Endpoint Manager – Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- **Azure AD grupo com todos os Salas do Teams em dispositivos Windows como membros** – um grupo criado em Azure AD que inclui todos os Salas do Teams em dispositivos Windows que devem fazer parte do serviço Salas do Microsoft Teams Premium. Esse grupo será usado para direcionar a implantação do agente MTR Pro.
  
> [!NOTE]
> Você pode considerar o uso de grupos dinâmicos em Azure AD para essa finalidade, mais informações em [Registrar Salas do Microsoft Teams em dispositivos Windows com Microsoft Endpoint Manager - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- Baixar **o instalador** do <https://aka.ms/serviceportalagentmsi> **agente MTR Pro** – baixe o arquivo zip do Agente e extraia o conteúdo do zip (ManagedRoomsInstaller.msi) para uma pasta temporária local.

**Para instalar usando Intune**

1. Entre no centro de [administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
1. Selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.
1. No painel **Selecionar tipo de aplicativo** , em **Outros** tipos de aplicativo, selecione **Aplicativo de linha de negócios**.
1. Clique **em Selecionar**. As etapas **Adicionar aplicativo** são exibidas. 
1. No painel **Adicionar aplicativo** , clique em **Selecionar arquivo de pacote de aplicativo**.
   1. No painel **Arquivo do pacote de** aplicativos, selecione  **Procurar**. Em seguida, selecione o arquivo **ManagedRoomsInstaller.msi** baixado anteriormente (consulte a seção pré-requisitos).
   1. Quando terminar, selecione **OK** no painel **de arquivos do pacote** de aplicativos para adicionar o aplicativo.
1. Na página **Informações do aplicativo** , execute as seguintes alterações:
   1. Publicador: **insira Microsoft Corporation**.
   1. Ignorar a versão do aplicativo: selecione **Sim**.

      > [!NOTE]
      > O agente do MTR Pro é auto-atualizado; portanto, você deve ignorar explicitamente a versão do aplicativo (qualquer versão da linha de base pode ser atualizada automaticamente).

   1. (Opcional) Categoria: selecione **Gerenciamento de Computadores**.
   
1. Clique em **Avançar** para exibir a página **Atribuições** .
   1. Na seção **Obrigatório** , clique em **+ adicionar grupo** para direcionar um grupo de dispositivos para instalação do agente.
   1. No painel **Selecionar grupo** , digite o nome do grupo na caixa Pesquisar (consulte pré-requisitos acima) e clique no **grupo** desejado e clique em **Selecionar**.
      Para obter mais informações, consulte [Adicionar grupos para organizar usuários e dispositivos](https://go.microsoft.com/fwlink/?linkid=2202166) e [Atribuir aplicativos a grupos com Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2202270).
1. Clique em **Avançar** para exibir a página **Revisar + criar** .
1. Examine os valores e as configurações inseridas para o aplicativo. Quando terminar, clique em **Criar** para adicionar o aplicativo ao Intune.

Depois que o processo for concluído, seus dispositivos começarão a instalar o agente MTR Pro após alguns minutos.

> [!NOTE]
> Após a instalação, o agente do MTR Pro pode levar até oito horas para executar uma auto-atualização para a versão mais recente e ser listado no portal do MTR Pro.
Para agilizar o registro automático no portal do MTR Pro, considere reiniciar o dispositivo MTR após a implantação do agente.

## <a name="completing-enrollment"></a>Concluindo o registro

Quando a instalação estiver concluída, aguarde de 5 a 10 minutos e atualize o portal para exibir o dispositivo na lista, relatado como Estado *de integração* .

No estado *de integração* , o status da sala é exibido e atualizado, mas não gera alertas nem cria tíquetes de investigação.

Escolha a sala e selecione **Registrar**  para começar a receber alertas de incidentes.

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>Desativar e desinstalar o software de monitoramento

Para cancelar o registro do dispositivo, remova o agente de monitoramento do dispositivo MTR da seguinte maneira:

1. No dispositivo que está sendo monitorado, faça logon no dispositivo como administrador. Certifique-se de seguir as *etapas em Executar operações como o Administração usuário do dispositivo*.
1. Baixe o script de redefinição de [aka.ms/MTRPDeviceOffBoarding](https://aka.ms/MTRPDeviceOffBoarding).
1. Extraia o script em algum lugar do dispositivo e copie o caminho.
1. Abra o PowerShell como administrador: no campo Windows ***Search** _ (seção inferior esquerda da tela), insira 'Powershell' e clique com o botão direito do mouse em _*_Windows PowerShell_**.
1. Selecione *"Executar como Administrador"* e aceite o prompt do UAC.
1. *Insira Set-ExecutionPolicy –ExecutionPolicy RemoteSigned* e pressione **Y** no próximo prompt.
1. Cole ou digite o caminho completo para o script de offboard descompactado na janela do PowerShell e pressione **Enter**.

   Exemplo:

   ```powershell
   C:\Users\admin\Downloads\MTRP\_Device\_Offboarding\MTRP\_Device\_Offboarding.ps1
   ```

   Esse comando redefine o dispositivo para atualizações MTR padrão do usuário e remove o agente de monitoramento MTR Pro e os arquivos.

1. No menu à esquerda no portal de Gerenciamento de Salas Microsoft Teams Pro, selecione **Salas**.
1. Na lista de salas fornecidas, escolha a sala que você deseja cancelar e selecione **Unenroll** para parar de receber alertas de incidentes ou tíquetes de investigação ou relatar um incidente para a sala.

## <a name="troubleshooting-table"></a>Tabela de solução de problemas

> [!NOTE]
> Todos os erros de monitoramento Salas Microsoft Teams Pro são registrados em um arquivo específico do Log de Eventos chamado **Microsoft Salas Gerenciadas**.

***Local do arquivo de log do runtime do aplicativo*** =

C:\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x\ServicePortalAgent\ServicePortal\_Verbose\_LogFile.log, onde **x.x.x** é o número da versão do aplicativo.

|Sintoma|Procedimento recomendado|
|---|---|
|Você recebe uma mensagem de erro informando: </p><p> ***ERRO: execute este aplicativo com** _ <br> Privilégios _ *_elevados_**|Execute o aplicativo com privilégios escalonados e tente novamente.|
|||
|Você recebe uma mensagem de erro informando: </p><p> ***Os dados TPM não podem ser encontrados***|Verifique se o dispositivo tem o TPM (Módulo de Plataforma Confiável) ativado em seu BIOS. Isso geralmente é encontrado nas configurações de segurança do BIOS do dispositivo.|
|||
|Você recebe uma mensagem de erro: </p><p> ***ERRO: Conta de usuário local chamada 'Administração' ou 'Skype' não encontrada***|Verifique se as contas de usuário existem no dispositivo certificado Microsoft sistemas do Teams Room.|
|||
|Você recebe mensagens de estado de erro que não estão cobertas acima.|Forneça uma cópia do log de instalação para o agente de suporte do Sistema do Teams Microsoft.|
