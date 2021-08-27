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
ms.localizationpriority: medium
description: 'A migração do aplicativo Estacionamento de Chamada inclui o provisionamento do pool do Skype for Business Server 2019 com qualquer música personalizada em arquivos de espera que tenham sido carregados na instalação herdada, restaurando as configurações de nível de serviço e retargeting all Call Park orbits to the Skype for Business Server 2019 pool. Se os arquivos personalizados de música em espera foram configurados no pool, esses arquivos precisam ser copiados para o novo pool Skype for Business Server 2019. Além disso, é recomendável que você faça backup de todos os arquivos de música em espera personalizados do Estacionamento de Chamada para outro destino para manter uma cópia de backup separada de todos os arquivos personalizados de música em espera que tenham sido carregados para o Estacionamento de Chamada. Os arquivos de música em espera personalizados para o aplicativo Estacionamento de Chamada são armazenados no armazenamento de arquivos do pool. Para copiar os arquivos de áudio de um armazenamento de arquivos de pool para um armazenamento de arquivos Skype for Business Server 2019, use o comando Xcopy com os seguintes parâmetros:'
ms.openlocfilehash: b8d2c5a898ca9ce4c2c1e8be4b9cbf3e7355a8cc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597535"
---
# <a name="migrate-call-park-application-settings"></a>Migrar configurações do aplicativo do Estacionamento de Chamada

A migração do aplicativo Estacionamento de Chamada inclui o provisionamento do pool do Skype for Business Server 2019 com quaisquer arquivos de música em espera personalizados que tenham sido carregados na instalação herdada, restaurando as configurações de nível de serviço e direcionando todas as órbitas do Estacionamento de Chamada para o pool do Skype for Business Server 2019. Se os arquivos personalizados de música em espera foram configurados no pool, esses arquivos precisam ser copiados para o novo pool Skype for Business Server 2019. Além disso, é recomendável que você faça backup de todos os arquivos de música em espera personalizados do Estacionamento de Chamada para outro destino para manter uma cópia de backup separada de todos os arquivos personalizados de música em espera que tenham sido carregados para o Estacionamento de Chamada. Os arquivos de música em espera personalizados para o aplicativo Estacionamento de Chamada são armazenados no armazenamento de arquivos do pool. Para copiar os arquivos de áudio de um armazenamento de arquivos de pool para um armazenamento de arquivos Skype for Business Server 2019, use o comando **Xcopy** com os seguintes parâmetros: 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Quando todos os arquivos de áudio personalizados foram copiados para o armazenamento de arquivos do Skype for Business Server 2019, as configurações do aplicativo Estacionamento de Chamada do pool do Skype for Business Server 2019 devem ser configuradas e os intervalos de órbita do Estacionamento de Chamada associados ao pool herdado devem ser reatribuídos ao pool Skype for Business Server 2019.

As configurações do aplicativo Estacionamento de Chamada incluem o limite de tempo limite de retirada, a habilitação ou desabilitação de música em espera, as tentativas máximas de retirada de chamada e a solicitação de tempo limite. Você deve gerenciar as configurações do aplicativo Estacionamento de Chamada usando o Shell de Gerenciamento Skype for Business Server para executar o cmdlet **Set-CsCpsConfiguration.** Não é possível gerenciar as configurações do aplicativo estacionamento de chamada usando o painel Skype for Business Server controle. 

## <a name="reconfigure-the-call-park-service-settings"></a>Reconfigurar o serviço de estacionamento de chamada Configurações

1. No servidor front-end Skype for Business Server 2019, abra o Shell Skype for Business Server Gerenciamento.

2. Na linha de comando, digite o seguinte:

    > [!NOTE]
    > Se as Skype for Business Server do aplicativo estacionamento de chamada 2019 são idênticas às configurações herdada, você pode ignorar esta etapa. Se as configurações do aplicativo Estacionamento de Chamada são diferentes para o Skype for Business Server 2019 e ambientes herdados, use o cmdlet abaixo como um modelo para atualizar essas alterações. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Para reatribuir todos os intervalos de órbita do Estacionamento de Chamada do pool herdado para o pool do Skype for Business Server 2019, você pode usar o Painel de Controle Skype for Business Server ou o Shell de Gerenciamento Skype for Business Server. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Reatribuir todos os Intervalos de Órbita de Estacionamento de Chamada usando Skype for Business Server Painel de Controle

1. Abra Skype for Business Server Painel de Controle.

2. No painel esquerdo, selecione **Recursos de Voz**.

3. Selecione a **guia Estacionamento de** Chamada. 

4. Para cada intervalo de órbitas do Estacionamento de Chamada atribuído a um pool herdado, edite o **FQDN** da configuração do servidor de destino e selecione o pool Skype for Business Server 2019 que processará as solicitações de Estacionamento de Chamada. 

5. Selecione **Confirmação** para salvar as alterações. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Reatribuir todos os Intervalos de Órbitas de Estacionamento de Chamada usando Skype for Business Server Shell de Gerenciamento

1. Abra Skype for Business Server Shell de Gerenciamento.

2. Na linha de comando, digite o seguinte:

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    Este cmdlet lista todos os intervalos de órbita do Estacionamento de Chamada na implantação. Todas as órbitas do Estacionamento de Chamada que tenham os parâmetros **CallParkServiceId** e **CallParkServerFqdn** definidos como o pool herdado devem ser reatribuídos. 

    Para reatribuir os intervalos de órbita herdados do Estacionamento de Chamada ao pool Skype for Business Server 2019, na linha de comando, digite o seguinte:

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Depois de reatribuir todos os intervalos de órbita do Estacionamento de Chamada para o pool do Skype for Business Server 2019, o processo de migração para o aplicativo Estacionamento de Chamada será concluído e o pool Skype for Business Server 2019 tratará de todas as solicitações futuras de Estacionamento de Chamada.


