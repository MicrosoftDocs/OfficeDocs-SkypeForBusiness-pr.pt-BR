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
description: 'A migração do aplicativo Estacionamento de Chamada inclui o provisionamento do pool do Skype for Business Server 2019 com qualquer música personalizada em espera que tenha sido carregada na instalação herdada, restaurando as configurações de nível de serviço e retargendo todas as órbitas do Estacionamento de Chamadas para o pool do Skype for Business Server 2019. Se arquivos de música de espera personalizados foram configurados no pool, esses arquivos precisam ser copiados para o novo pool do Skype for Business Server 2019. Além disso, é recomendável que você faça backup de todos os arquivos de música de espera personalizados do Estacionamento de Chamada de outro destino para manter uma cópia de backup separada de todos os arquivos de música de espera personalizados que foram carregados para o Estacionamento de Chamada. Os arquivos de música de espera personalizados para o aplicativo Estacionamento de Chamada são armazenados no armazenamento de arquivos do pool. Para copiar os arquivos de áudio de um armazenamento de arquivos de pool para um armazenamento de arquivos do Skype for Business Server 2019, use o comando Xcopy com os seguintes parâmetros:'
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752813"
---
# <a name="migrate-call-park-application-settings"></a>Migrar configurações do aplicativo do Estacionamento de Chamada

A migração do aplicativo Estacionamento de Chamada inclui o provisionamento do pool do Skype for Business Server 2019 com qualquer arquivo de música de espera personalizado que tenha sido carregado na instalação herdada, restaurando as configurações de nível de serviço e direcionando todas as órbitas de Estacionamento de Chamadas para o pool do Skype for Business Server 2019. Se arquivos de música de espera personalizados foram configurados no pool, esses arquivos precisam ser copiados para o novo pool do Skype for Business Server 2019. Além disso, é recomendável que você faça backup de todos os arquivos de música de espera personalizadas do Estacionamento de Chamada em outro destino para manter uma cópia de backup separada de qualquer arquivo de música de espera personalizado que tenha sido carregado para o Estacionamento de Chamada. Os arquivos de música de espera personalizados para o aplicativo Estacionamento de Chamada são armazenados no armazenamento de arquivos do pool. Para copiar os arquivos de áudio de um armazenamento de arquivos de pool para um armazenamento de arquivos do Skype for Business Server 2019, use o comando **Xcopy** com os seguintes parâmetros: 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Quando todos os arquivos de áudio personalizados são copiados para o armazenamento de arquivos do Skype for Business Server 2019, as configurações do aplicativo Estacionamento de Chamada do pool do Skype for Business Server 2019 devem ser configuradas, e os intervalos de órbita do Estacionamento de Chamadas associados ao pool herdado devem ser reatribuídos ao pool do Skype for Business Server 2019.

As configurações do aplicativo Estacionamento de Chamada incluem o limite de tempo limite de retirada, a habilitação ou desabilitação de música em espera, o máximo de tentativas de atendimento de chamada e a solicitação de tempo limite. Você deve gerenciar as configurações do aplicativo Estacionamento de Chamadas usando o Shell de Gerenciamento do Skype for Business Server para executar o cmdlet **Set-CsCpsConfiguration.** Você não pode gerenciar as configurações do aplicativo Estacionamento de Chamadas usando o Painel de Controle do Skype for Business Server. 

## <a name="reconfigure-the-call-park-service-settings"></a>Reconfigurar as Configurações do Serviço de Estacionamento de Chamada

1. No Servidor front-end do Skype for Business Server 2019, abra o Shell de Gerenciamento do Skype for Business Server.

2. Na linha de comando, digite o seguinte:

    > [!NOTE]
    > Se as configurações do aplicativo Estacionamento de Chamada do Skype for Business Server 2019 são idênticas às configurações herdada, ignore esta etapa. Se as configurações do aplicativo Estacionamento de Chamada são diferentes para o Skype for Business Server 2019 e ambientes herdados, use o cmdlet abaixo como um modelo para atualizar essas alterações. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Para reatribuir todos os intervalos de órbitas do Estacionamento de Chamadas do pool herdado para o pool do Skype for Business Server 2019, você pode usar o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Reatribuir todos os intervalos de órbita de estacionamento de chamada usando o Painel de Controle do Skype for Business Server

1. Abra o Painel de Controle do Skype for Business Server.

2. No painel esquerdo, selecione Recursos **de Voz.**

3. Selecione a **guia Estacionamento de** Chamada. 

4. Para cada intervalo de órbita de Estacionamento de Chamadas atribuído a um pool herdado, edite o **FQDN** da configuração do servidor de destino e selecione o pool do Skype for Business Server 2019 que processará as solicitações de Estacionamento de Chamadas. 

5. Selecione **Confirmação** para salvar as alterações. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Reatribuir todos os intervalos de órbitas de estacionamento de chamada usando o Shell de Gerenciamento do Skype for Business Server

1. Abra o Shell de Gerenciamento do Skype for Business Server.

2. Na linha de comando, digite o seguinte:

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    Este cmdlet lista todos os intervalos de órbitas do Estacionamento de Chamada na implantação. Todas as órbitas de Estacionamento de Chamada que tenham os parâmetros **CallParkServiceId** e **CallParkServerFqdn** definidos como o pool herdado devem ser reatribuídos. 

    Para reatribuir os intervalos de órbita do Estacionamento de Chamadas herdados ao pool do Skype for Business Server 2019, na linha de comando, digite o seguinte:

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Depois de reatribuir todos os intervalos de órbitas do Estacionamento de Chamadas ao pool do Skype for Business Server 2019, o processo de migração para o aplicativo Estacionamento de Chamadas será concluído e o pool do Skype for Business Server 2019 lidará com todas as solicitações futuras de Estacionamento de Chamadas.


