---
title: Migrar configurações do aplicativo de estacionamento de chamada
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'A migração do aplicativo inclui o Skype para Business Server 2019 pool com qualquer música personalizada em espera arquivos carregados na instalar herdado de provisionamento de estacionamento de chamada, restaurando as configurações de nível de serviço e redirecionando estacionamento de chamada todas as Órbitas para o Skype para Business Server 2019 pool. Se os arquivos de música de espera personalizados tiverem sido configurados no pool, esses arquivos precisam ser copiados para o novo Skype para Business Server 2019 pool. Além disso, é recomendável que você fazer backup de qualquer estacionamento de chamada personalizado arquivos de música de espera para outro destino para manter uma cópia de backup separada de qualquer música de espera arquivos personalizados que foram carregados para estacionamento de chamadas. Os arquivos de música de espera personalizados para o aplicativo de estacionamento de chamada são armazenados no armazenamento de arquivos do pool. Para copiar os arquivos de áudio de um repositório de arquivo do pool para um Skype para Business Server 2019 file store, use o comando Xcopiar com os seguintes parâmetros:'
ms.openlocfilehash: a91c23f06d22d822567bd39ec9f18eb7289e201d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028821"
---
# <a name="migrate-call-park-application-settings"></a>Migrar configurações do aplicativo de estacionamento de chamada

A migração do aplicativo estacionamento de chamadas inclui o provisionamento do Skype para Business Server 2019 pool com quaisquer arquivos de música de espera personalizados que foram carregados na instalar herdado, restaurando as configurações de nível de serviço e o direcionamento novamente todas as Órbitas de estacionamento de chamada para o Skype para Business Server 2019 pool. Se os arquivos de música de espera personalizados tiverem sido configurados no pool, esses arquivos precisam ser copiados para o novo Skype para Business Server 2019 pool. Além disso, é recomendável que você fazer backup de qualquer estacionamento de chamada personalizado arquivos de música de espera para outro destino para manter uma cópia de backup separada de qualquer música de espera arquivos personalizados que foram carregados para estacionamento de chamadas. Os arquivos de música de espera personalizados para o aplicativo de estacionamento de chamada são armazenados no armazenamento de arquivos do pool. Para copiar os arquivos de áudio de um repositório de arquivo do pool para um Skype para Business Server 2019 file store, use o comando **Xcopiar** com os seguintes parâmetros: 
  
```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Quando todos os arquivos de áudio personalizados foram copiados para o Skype para Business Server 2019 file store, as configurações do aplicativo de estacionamento de chamada do Skype para o servidor de negócios 2019 pool deve ser configurado e estacionamento de chamada órbita intervalos que estão associados ao pool herdado devem ser reatribuídos para o Skype para Business Server 2019 pool.
  
As configurações do aplicativo de estacionamento de chamada incluem o limite de tempo limite de retirada, habilitando ou desabilitando a música em espera, as tentativas de retirada de máximo de chamadas e a solicitação de tempo limite. Você deve gerenciar configurações do aplicativo de estacionamento de chamada usando o Skype para Business Server Management Shell para executar o cmdlet **Set-CsCpsConfiguration** . Você não pode gerenciar as configurações do aplicativo de estacionamento de chamada usando o Skype para painel de controle do servidor de negócios. 
  
## <a name="reconfigure-the-call-park-service-settings"></a>Reconfigurar as definições do serviço de estacionamento de chamada

1. Em Skype para Business Server 2019 servidor Front-End, abra o Skype do Shell de gerenciamento do servidor de negócios.
    
2. Na linha de comando, digite o seguinte:
    
    > [!NOTE]
    > Se seu Skype para configurações de aplicativo de negócios Server 2019 Call Park é idêntica às configurações herdadas, você poderá ignorar esta etapa. Se as configurações do aplicativo de estacionamento de chamada são diferentes para o Skype para ambientes de legado e Business Server 2019, use o cmdlet abaixo como modelo para atualizar essas alterações. 
  
  ```
  Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
  
  ```

Para reatribuir todos os intervalos de órbita estacionamento de chamada do pool herdado para o Skype para Business Server 2019 pool, você pode usar o Skype para painel de controle do Business Server ou o Skype do Shell de gerenciamento do servidor de negócios. 
  
## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Reatribuir todos os intervalos de órbita de estacionamento de chamada usando o Skype para painel de controle do servidor de negócios

1. Abra o Skype para painel de controle do servidor de negócios.
    
2. No painel esquerdo, selecione **Os recursos de voz**.
    
3. Selecione a guia **Estacionamento de chamadas** . 
    
4. Para cada intervalo de órbita de estacionamento de chamadas atribuído a um pool herdado, edite a definição de **FQDN do servidor de destino** e selecione o Skype para pool de negócios Server 2019 que processará as solicitações do estacionamento de chamadas. 
    
5. Selecione **Confirmar** para salvar as alterações. 
    
## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Reatribuir todos os intervalos de órbita de estacionamento de chamada usando o Skype para Business Server Management Shell

1. Abra o Skype do Shell de gerenciamento do servidor de negócios.
    
2. Na linha de comando, digite o seguinte:
    
  ```
  Get-CsCallParkOrbit
  ```

    Esse cmdlet lista todos os intervalos de órbita de estacionamento de chamada na implantação. Todas as Órbitas de estacionamento de chamada com os parâmetros **CallParkServiceId** e **CallParkServerFqdn** definido como o pool herdado devem ser reatribuídas. 
    
    Para reatribuir a órbita de estacionamento de chamada herdada intervalos para o Skype para pool de negócios 2019 de servidor, na linha de comando, digite o seguinte:
    
  ```
  Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
  
  ```

Depois de reatribuir todos os intervalos de órbita de estacionamento de chamada para o Skype para Business Server 2019 pool, o processo de migração para o aplicativo de estacionamento de chamada será concluído e o Skype para Business Server 2019 pool lidará com todas as solicitações futuras de estacionamento de chamadas.
  

