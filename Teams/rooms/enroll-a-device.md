---
title: Registrar um Teams room nos Serviços Gerenciados
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Integrando Salas do Teams para serviços gerenciados
f1keywords: ''
ms.openlocfilehash: 4261e93a7bfab5d21620f8dbb327575352062c86
ms.sourcegitcommit: abe942c294ed5fca70efdf039d38d611b9c21fe9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2022
ms.locfileid: "63689051"
---
# <a name="enroll-device-into-managed-service"></a>Registrar dispositivo no Serviço Gerenciado

A implantação requer a integração Salas do Microsoft Teams dispositivos para os Salas do Microsoft Teams gerenciados. O agente de serviço de monitoramento deve ser usado com sistemas Microsoft Teams MTR (Room) certificados e periféricos.

## <a name="prerequisites"></a>Pré-requisitos

Siga estes procedimentos para configurar o hardware antes de tentar o processo de registro:

### <a name="adding-proxy-settings-optional"></a>Adicionando configurações de proxy (opcional)

1. Faça logon como administrador seguindo [a execução de operações como o usuário administrador do dispositivo MTR](#performing-operations-as-the-admin-user-of-the-mtr-device).
1. No campo Windows ***Search** _ (seção inferior esquerda da tela), digite _ *cmd** (pressione a tela ou selecione à direita e escolha **_Executar como administrador_**).  
1. Execute o seguinte comando (aspas duplas no final do comando são importantes):
   - Se estiver usando um ***único servidor proxy***: bitsadmin /Util /SetIEProxy LOCALSYSTEM <proxyserver>MANUAL_PROXY :<port> ""

      *Exemplo:* bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY contosoproxy.corp.net:8080 ""
      

   - Se estiver usando um ***arquivo pac*** : bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url>

      
      *Exemplo:* bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT `http://contosoproxy.corp.net/proxy.pac`
      

### <a name="enabling-tpm-settings"></a>Habilitando configurações do TPM

> [!NOTE]
> O TPM deve estar habilitado para se inscrever no serviço gerenciado.

Se o TPM em um dispositivo Intel NUC estiver desabilitado, habilita o TPM nesses dispositivos da seguinte forma:  

1. Conecte o teclado a um dispositivo NUC.  
1. Reiniciar dispositivo.  
1. Para exibir a tela do BIOS, pressione rapidamente **F2**.  
1. Selecione **Avançado**.  
1. Selecione **Segurança**.  
1. No lado direito abaixo dos Recursos de Segurança, habilita a **Tecnologia de Confiança da Plataforma Intel**.  
1. Para salvar suas configurações, pressione **F10**.  
1. Na caixa de confirmação, selecione **Sim**. 
## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>Executando operações como o usuário administrador do dispositivo MTR

Alguns procedimentos de configuração/instalação exigem que você faça logoff no dispositivo como Administrador.

Para fazer logoff no dispositivo como Administrador (administrador local):

1. Certifique-se de desligar todas as chamadas em andamento e retornar à tela inicial.
1. Na interface de usuário da sala Microsoft Teams, selecione **Mais e,** em seguida, selecione **Configurações**, onde você é solicitado a obter a senha de Administrador local no dispositivo (a senha padrão é **_sfb_**).
1. Selecione **Configurações** e selecione **Windows Configurações** para acessar Windows como administrador local.  

1. Na lista de usuários exibidos na tela de logon Windows, selecione **Administrador** (ou o respectivo administrador local do seu dispositivo).

> [!NOTE]
> Se o *computador estiver* ingressado no domínio, escolha Outro **Usuário e use** **.\admin** ou o nome de usuário do administrador local configurado no dispositivo como o nome de usuário.  

Para retornar ao aplicativo Microsoft Teams Room após executar as tarefas administrativas necessárias:

1. No Windows ***menu Iniciar***, saia da conta Administrador.
1. Volte para Microsoft Teams Sala selecionando o ícone da conta de usuário no lado esquerdo da tela e selecionando **Skype**.

> [!NOTE]
> Se o Skype usuário não estiver listado, selecione Outro Usuário e insira ***.\skype*** como o nome de usuário e entre.

 

## <a name="urls-required-for-communication"></a>URLs necessárias para comunicação

 > [!NOTE]
 > Todo o tráfego de rede entre o agente de dispositivos MTR e o portal de serviço Salas do Microsoft Teams – Serviços Gerenciados é SSL sobre a porta 443 *.*  Consulte [Office 365 URLs e intervalos de endereços IP - Microsoft 365 Enterprise | Microsoft Docs](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

Os hosts a seguir devem ser permitidos se você tiver a lista de permissão de **tráfego** habilitada em seu ambiente empresarial:

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

O processo de inscrição envolve estas etapas:  

1. Na barra de navegação esquerda do portal Salas do Microsoft Teams – Serviços Gerenciados [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/), expanda **Configurações** e selecione **Geral**.  
1. Em *Registrar uma sala*, selecione **Baixar instalador**  para baixar o software do agente de monitoramento.
1. **Opcional:** Configurar configurações de proxy para o agente; consulte [Adicionando configurações de proxy (opcional)](#adding-proxy-settings-optional).
1. Instale o instalador do agente (baixado na etapa 2) em unidades MTR, executando o MSI localmente em um dispositivo MTR ou por meio de seus meios normais de publicação de aplicativos MSI em massa para dispositivos em seu ambiente (Política de Grupo etc.)  
1. A sala aparece no portal dentro de 5 a 10 minutos. Se isso não acontecer, entre em contato managedroomsupport@microsoft.com.  

   ![Captura de tela de configurações e chaves de registro próprio.](../media/software-installation-005new.png)
 
> [!NOTE]
> Se você precisar instalar o agente sem o aplicativo Teams no MTR podendo fazer logon no Teams, você pode usar nossa chave de registro como um processo opcional. Vá para '?'  (Ajuda) no canto superior direito do portal e selecione 'Baixar chave (opcional)'. Ao instalar o agente, coloque a "Chave de Auto-Registro" (baixada anteriormente do portal) em  **theC:\Rigeldirectory**  do dispositivo.

## <a name="installation"></a>Instalação

Depois de baixar o instalador da Microsoft (a partir do portal ou usando a URL AKA.ms fornecida acima), descompa azip seu conteúdo para acessar o arquivo **ManagedRoomsInstaller.msi.**

Há dois modos de instalação: 1) instalação de máquina local individual e 2) modo de implantação em massa (geralmente por meio de política de grupo de método semelhante). Recomendamos a instalação individual para máquinas que não ingressam no domínio ou para máquinas que você não tem como executar os instaladores MSI remotamente.  

Devido às várias maneiras variadas nas quais os clientes podem executar aplicativos MSI no modo de implantação em massa, este documento percorre somente a instalação no modo individual.  
## <a name="individual-devicemdashdomain-joined-walkthrough"></a>Passo a passo individual ingressado em DeviceDomain&mdash;

1. Faça logoff no dispositivo como administrador. *Certifique-se de que as operações de execução como o usuário administrador das etapas do* dispositivo sejam seguidas.

1. Copie o arquivo **ManagedRoomsInstaller.msi** para o dispositivo MTR.

   Ao executar o ***ManagedRoomsInstaller.msi*** é uma tela de Contrato de Licença.

1.  Depois de ler o contrato, verifique ***Aceito os termos** no Contrato de Licença_ e pressione _*Install**.  

    Isso inicia a instalação do Salas do Microsoft Teams – software de monitoramento de Serviços Gerenciados. Um prompt de elevação (executado como administrador) é exibido.

 1. Selecione **Sim**.

    A instalação continuará. Durante o procedimento de instalação, uma janela de console é aberta e inicia o estágio final da instalação de software de monitoramento Salas do Microsoft Teams – Serviços Gerenciados.  

    > [!NOTE]
    > Não feche a janela. Depois que a instalação for concluída, o assistente exibirá um botão "Concluir".

## <a name="completing-enrollment"></a>Concluindo o registro

Depois que a instalação for concluída, aguarde de 5 a 10 minutos e atualize o portal e o dispositivo será listado, relatado como *estado de* integração.

No *estado de Integração* , o status da sala é exibido e atualizado, mas não gerará alertas ou criará tíquetes de investigação.

Escolha a sala e selecione **Registrar para**  começar a receber alertas de incidentes, tíquetes de investigação ou para relatar um incidente.

Para dúvidas ou problemas, abra um incidente relatado pelo cliente no portal ou entre em contato managedroomsupport@microsoft.com.

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>Desinstalar e desinstalar software de monitoramento

Para desemrollar o dispositivo, remova o agente de monitoramento do dispositivo MTR da seguinte forma:

1. No dispositivo que está sendo monitorado, faça logoff no dispositivo como administrador. Siga as etapas em *Executar operações como o usuário administrador do dispositivo*.
1. Baixe o script de redefinição [aka.ms/MTRPDeviceOffBoarding](https://aka.ms/MTRPDeviceOffBoarding).
1. Extraia o script em algum lugar no dispositivo e copie o caminho.
1. Abra o PowerShell como administrador: no campo Windows ***Search** _ (seção inferior esquerda da tela), digite 'Powershell' e clique com o botão direito do mouse em _*_Windows PowerShell_**.
1. Selecione *"Executar como Administrador"* e aceite o prompt UAC.
1. Insira *Set-ExecutionPolicy –ExecutionPolicy RemoteSigned* e pressione **Y** no próximo prompt.  
1. Colar ou digitar o caminho completo para o script de offboard desacortado na janela do PowerShell e pressione **Enter**.

   Exemplo:

   *C:\Users\admin\Downloads\MTRPDeviceOffboarding\_\_\MTRPDevice\_\_Offboarding.ps1*  

   Isso redefine o dispositivo para atualizações MTR padrão do usuário e remove o agente de monitoramento MTRP e os arquivos.

1. No menu à esquerda no portal Salas do Microsoft Teams – Serviços Gerenciados, selecione **Salas**.  
1. Na lista de salas fornecidas, escolha a sala que você deseja desem andamento e selecione **Desem** andamento para parar de receber alertas de incidentes ou tíquetes de investigação ou para relatar um incidente para a sala.

## <a name="troubleshooting-table"></a>Tabela de solução de problemas

> [!NOTE]
> Todos Salas do Microsoft Teams – Os erros de monitoramento dos Serviços Gerenciados são registrados em um arquivo de Log de Eventos específico chamado **Salas Gerenciadas da Microsoft**. 

### <a name="application-runtime-log-file-location-"></a>***Local do arquivo de log do tempo de execução do aplicativo*** =  

C:\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x.x\ServicePortalAgent\ServicePortalVerboseLogFile.log\_\_, onde **x.x.x** é o número da versão do aplicativo.

|**Sintoma**  |**Procedimento recomendado**  |
| :- | :- |
|<p>Você recebe uma mensagem de erro informando   </p><p>***ERRO: Execute este aplicativo com** _ </p><p>Privilégios *__elevated_**  </p>|Execute o aplicativo com privilégios escalonados e tente novamente  |
|  |  |
|<p>Você recebe uma mensagem de erro informando   </p><p>***Dados do TPM não podem ser encontrados***  </p>|Verifique se seu dispositivo tem o TPM (Trusted Platform Module) ligado em seu BIOS. Isso geralmente é encontrado nas configurações de segurança do BIOS do dispositivo  |
|  |  |
|<p>Você recebe uma mensagem de erro  </p><p>` `***ERRO: conta de usuário local denominada 'Admin' ou 'Skype' não encontrada***  </p>|Certifique-se de que as contas de usuário existam no dispositivo Microsoft Teams de sala certificado.  |
|  |  |
|Você recebe qualquer mensagem de estado de erro que não seja abordada acima  |Forneça uma cópia do log de instalação ao seu Microsoft Teams de suporte do sistema. |
