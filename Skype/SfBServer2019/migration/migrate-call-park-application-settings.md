---
title: Migrar configurações do aplicativo do Estacionamento de Chamada
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'A migração do aplicativo de estacionamento de chamada inclui o provisionamento do pool do Skype for Business Server 2019 com qualquer música personalizada em arquivos de espera que foram carregados na instalação herdada, restaurando as configurações de nível de serviço e redirecionando todas as órbitas do estacionamento de chamadas para o pool do Skype for Business Server 2019. Se os arquivos de música em espera personalizados tiverem sido configurados no pool, esses arquivos precisam ser copiados para o novo pool do Skype for Business Server 2019. Além disso, é recomendável que você faça o backup de todos os arquivos de música em espera do estacionamento de chamadas de para outro destino para manter uma cópia de backup separada de qualquer arquivo de música em espera personalizado que tenha sido carregado para estacionamento de chamada. Os arquivos de música em espera personalizados para o aplicativo de estacionamento de chamada são armazenados no repositório de arquivos do pool. Para copiar os arquivos de áudio de um repositório de arquivos de pool para um repositório de arquivos do Skype for Business Server 2019, use o comando xcopy com os seguintes parâmetros:'
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752813"
---
# <a name="migrate-call-park-application-settings"></a>Migrar configurações do aplicativo do Estacionamento de Chamada

A migração do aplicativo de estacionamento de chamada inclui o provisionamento do pool do Skype for Business Server 2019 com qualquer arquivo de música em espera personalizado que tenha sido carregado na instalação herdada, restaurando as configurações de nível de serviço e redirecionando todas as órbitas do estacionamento de chamadas para o pool do Skype for Business Server 2019. Se os arquivos de música em espera personalizados tiverem sido configurados no pool, esses arquivos precisam ser copiados para o novo pool do Skype for Business Server 2019. Além disso, é recomendável que você faça o backup de todos os arquivos de música em espera do estacionamento de chamadas para outro destino, para manter uma cópia de backup separada de qualquer arquivo de música em espera personalizado que tenha sido carregado para estacionamento de chamada. Os arquivos de música em espera personalizados para o aplicativo de estacionamento de chamada são armazenados no repositório de arquivos do pool. Para copiar os arquivos de áudio de um repositório de arquivos de pool para um repositório de arquivos do Skype for Business Server 2019, use o comando **xcopy** com os seguintes parâmetros: 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Quando todos os arquivos de áudio personalizados foram copiados para o repositório de arquivos do Skype for Business Server 2019, as configurações de aplicativo de estacionamento de chamada do pool do Skype for Business Server 2019 devem ser configuradas, e os intervalos de órbita de estacionamento de chamada associados ao pool herdado devem ser reatribuídos ao pool 2019 do Skype for Business Server.

As configurações do aplicativo de estacionamento de chamada incluem o limite de tempo limite de retirada, habilitando ou desabilitando a música em espera, as tentativas máximas de recebimento de chamadas e a solicitação de tempo limite. Você deve gerenciar as configurações do aplicativo de estacionamento de chamadas usando o Shell de gerenciamento do Skype for Business Server para executar o cmdlet **set-CsCpsConfiguration** . Você não pode gerenciar as configurações do aplicativo de estacionamento de chamada usando o painel de controle do Skype for Business Server. 

## <a name="reconfigure-the-call-park-service-settings"></a>Reconfigurar as definições do serviço de estacionamento de chamadas

1. No servidor front-end do Skype for Business Server 2019, abra o Shell de gerenciamento do Skype for Business Server.

2. Na linha de comando, digite o seguinte:

    > [!NOTE]
    > Se as configurações do aplicativo de estacionamento de chamada do Skype for Business Server 2019 são idênticas às configurações herdadas, você pode ignorar esta etapa. Se as configurações do aplicativo de estacionamento de chamada forem diferentes para o Skype for Business Server 2019 e ambientes herdados, use o cmdlet abaixo como um modelo para atualizar essas alterações. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Para reatribuir todos os intervalos de órbita de estacionamento de chamadas do pool herdado para o pool do Skype for Business Server 2019, você pode usar o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Reatribuir todos os intervalos de órbita de estacionamento de chamada usando o painel de controle do Skype for Business Server

1. Abra o painel de controle do Skype for Business Server.

2. No painel esquerdo, selecione **recursos de voz**.

3. Selecione a guia **estacionamento de chamada** . 

4. Para cada intervalo de órbita de estacionamento de chamada atribuído a um pool herdado, edite o **FQDN da configuração do servidor de destino** e selecione o pool do Skype for Business Server 2019 que processará as solicitações de estacionamento de chamadas. 

5. Selecione **confirmar** para salvar as alterações. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Reatribuir todos os intervalos de órbita de estacionamento de chamadas usando o Shell de gerenciamento do Skype for Business Server

1. Abra o Shell de gerenciamento do Skype for Business Server.

2. Na linha de comando, digite o seguinte:

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    Este cmdlet lista todos os intervalos de órbita de estacionamento de chamada na implantação. Todas as órbitas de estacionamento de chamadas com os parâmetros **CallParkServiceId** e **CallParkServerFqdn** definidos como o pool herdado devem ser reatribuídas. 

    Para reatribuir os intervalos de órbita de estacionamento de chamada herdado para o pool do Skype for Business Server 2019, na linha de comando, digite o seguinte:

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Após reatribuir todos os intervalos de órbita de estacionamento de chamada ao pool do Skype for Business Server 2019, o processo de migração para o aplicativo de estacionamento de chamada será concluído e o pool do Skype for Business Server 2019 tratará de todas as solicitações de estacionamento de chamadas futuras.


