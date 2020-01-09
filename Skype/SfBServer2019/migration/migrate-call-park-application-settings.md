---
title: Migrar configurações do aplicativo do Estacionamento de Chamada
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'A migração do aplicativo de estacionamento de chamadas inclui o provisionamento do pool do Skype for Business Server 2019 com qualquer música personalizada em arquivos de retenção que foram carregados na instalação herdada, a restauração das configurações de nível de serviço e o redirecionamento de todas as órbitas do estacionamento de chamada para o Pool do Skype for Business Server 2019. Se os arquivos de música em espera personalizados tiverem sido configurados no pool, esses arquivos precisarão ser copiados para o novo pool do Skype for Business Server 2019. Além disso, é recomendável que você faça backup de todos os arquivos de música em espera personalizados de qualquer telefone para outro destino para manter uma cópia de backup separada de todos os arquivos de música em espera personalizados que foram carregados para o parque da chamada. Os arquivos de música em espera personalizados para o aplicativo de estacionamento de chamadas são armazenados no repositório de arquivos do pool. Para copiar os arquivos de áudio de um repositório de arquivos de pool para um repositório de arquivos do Skype for Business Server 2019, use o comando xcopy com os seguintes parâmetros:'
ms.openlocfilehash: 0435144fc647a08d8252f35d8449d1e7daa62d68
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991156"
---
# <a name="migrate-call-park-application-settings"></a>Migrar configurações do aplicativo do Estacionamento de Chamada

A migração do aplicativo de estacionamento de chamadas inclui o provisionamento do pool do Skype for Business Server 2019 com qualquer arquivo de música em espera personalizado que tenha sido carregado na instalação herdada, restauração das configurações do nível de serviço e redirecionamento de todas as órbitas do estacionamento de chamada ao pool do Skype for Business Server 2019. Se os arquivos de música em espera personalizados tiverem sido configurados no pool, esses arquivos precisarão ser copiados para o novo pool do Skype for Business Server 2019. Além disso, é recomendável que você faça backup de qualquer chamada personalizada em arquivos de música em espera para outro destino para manter uma cópia de backup separada de todos os arquivos de música em espera personalizados que foram carregados para o parque de chamadas. Os arquivos de música em espera personalizados para o aplicativo de estacionamento de chamadas são armazenados no repositório de arquivos do pool. Para copiar os arquivos de áudio de um repositório de arquivos de pool para um repositório de arquivos do Skype for Business Server 2019, use o comando **xcopy** com os seguintes parâmetros: 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Quando todos os arquivos de áudio personalizados foram copiados para o repositório de arquivos do Skype for Business Server 2019, as configurações do aplicativo de estacionamento de chamada do pool do Skype for Business Server 2019 devem ser configuradas e os intervalos de estacionador de chamadas em órbita associados ao pool herdado deve ser reatribuído ao pool do Skype for Business Server 2019.

As configurações do aplicativo de estacionamento de chamada incluem o limite de tempo limite de separação, habilitando ou desabilitando música em espera, o número máximo de tentativas de chamadas e a solicitação de tempo limite. Você deve gerenciar as configurações do aplicativo parque de chamadas usando o Shell de gerenciamento do Skype for Business Server para executar o cmdlet **set-CsCpsConfiguration** . Não é possível gerenciar as configurações do aplicativo parque de chamadas usando o painel de controle do Skype for Business Server. 

## <a name="reconfigure-the-call-park-service-settings"></a>Reconfigurar as configurações de serviço do estacionamento de chamada

1. No servidor front-end do Skype for Business Server 2019, abra o Shell de gerenciamento do Skype for Business Server.

2. Na linha de comando, digite o seguinte:

    > [!NOTE]
    > Se as configurações do aplicativo parque de chamadas do Skype for Business Server 2019 forem idênticas às configurações herdadas, você poderá ignorar esta etapa. Se as configurações do aplicativo de estacionamento de chamada forem diferentes para o Skype for Business Server 2019 e ambientes herdados, use o cmdlet abaixo como um modelo para atualizar essas alterações. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Para reatribuir todos os intervalos órbitas do estacionamento de chamadas do pool herdado ao pool do Skype for Business Server 2019, você pode usar o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Reatribuir todas as faixas órbitas do estacionamento de chamadas usando o painel de controle do Skype for Business Server

1. Abra o painel de controle do Skype for Business Server.

2. No painel esquerdo, selecione **recursos de voz**.

3. Selecione a guia **estacionamento de chamadas** . 

4. Para cada intervalo de linha de plano de chamada atribuída a um pool herdado, edite a configuração do **FQDN do servidor de destino** e selecione o pool do Skype for Business Server 2019 que processará as solicitações de estacionamento de chamadas. 

5. Selecione **confirmar** para salvar as alterações. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Reatribuir todas as faixas órbitas do estacionamento de chamadas usando o Shell de gerenciamento do Skype for Business Server

1. Abrir o Shell de gerenciamento do Skype for Business Server.

2. Na linha de comando, digite o seguinte:

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    Esse cmdlet lista todos os intervalos de o parque de chamadas órbitas na implantação. Todas as órbitas do estacionamento de chamada com os parâmetros **CallParkServiceId** e **CallParkServerFqdn** definidas como o pool herdado devem ser reatribuídas. 

    Para reatribuir os intervalos de linha de chamada de barra de chamadas herdadas ao pool do Skype for Business Server 2019, na linha de comando, digite o seguinte:

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Depois de reatribuir todos os intervalos de chamada de estacionamento de chamada ao pool do Skype for Business Server 2019, o processo de migração para o aplicativo de estacionamento de chamadas será concluído e o pool do Skype for Business Server 2019 cuidará de todas as solicitações de suporte ao parque do Skype.


