---
title: Criar definições de configuração de Qualidade da Experiência no Skype for Business Server
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
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Resumo: saiba mais sobre as configurações de QoE (Qualidade da Experiência) no Skype for Business Server.'
ms.openlocfilehash: d1d0b299b5cf0bbaf3627b7c90f90e7e1d958d10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816991"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Criar definições de configuração de Qualidade da Experiência no Skype for Business Server
 
**Resumo:** Saiba mais sobre as configurações de QoE (Qualidade da Experiência) no Skype for Business Server.
  
Os atributos métricos da Qualidade da Experiência (QoE) rastreiam a qualidade das chamadas de áudio e vídeo feitas na organização, inclusive o número de pacotes de rede perdidos, o ruído de fundo e a quantidade de "jitter" (diferenças no atraso de pacotes). Esses atributos métricos são armazenados em um banco de dados separado de outros dados (como registros de detalhes das chamadas), permitindo a habilitação e desabilitação do QoE, independentemente de outros registros de dados.
  
Quando você instala o Skype for Business Server, um único conjunto global de definições de configuração de QoE é criado para você. Os administradores também podem ter a opção de criar configurações personalizadas no escopo local. Sempre que estas configurações de escopo local são usadas, elas têm precedência sobre as configurações globais. Por exemplo, se você criar configurações de escopo de site para o site Redmond, essas configurações (em vez das configurações globais) serão usadas para gerenciar a QoE em Redmond.
  
As definições de configuração de QoE podem ser criadas usando o Painel de Controle do Skype for Business Server ou o cmdlet [New-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) Se você estiver usando o Painel de Controle do Skype for Business Server para criar novas configurações, as seguintes opções estarão disponíveis:
  
|**Configuração da interface do usuário**|**Parâmetro do PowerShell**|**Descrição**|
|:-----|:-----|:-----|
|Nome  <br/> |Identidade  <br/> |Identificador exclusivo das configurações a serem criadas. As definições de configuração de QoE só podem ser criadas no escopo do site.  <br/> |
|Habilitar o monitoramento de dados de QoE  <br/> |EnableQoE  <br/> |Especifica se os registros QoE serão coletados e salvos no banco de dados de monitoramento.  <br/> |
|Habilitar a purgação de dados de QoE  <br/> |EnablePurging  <br/> |Especifica se os registros serão limpos após a duração definida na propriedade Manter dados de QoE por um período máximo **de (dias)** decorrido. <br/> |
|Manter dados de QoE por um período máximo (dias)  <br/> |KeepQoEDataForDays  <br/> |Número de dias em que os dados de QoE serão armazenados antes de serem limpos do banco de dados. Esse valor será ignorado se a purgação estiver desabilitada.  <br/> |
   
> [!NOTE]
> O New-CsQoEConfiguration cmdlet inclui opções adicionais não disponíveis no Painel de Controle do Skype for Business Server. Para obter mais informações, consulte o tópico de ajuda [New-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para criar definições de configuração de QoE usando o Painel de Controle do Skype for Business Server

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.  
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Dados da Qualidade da Experiência**.
    
4. Na página **Dados de Qualidade da Experiência,** clique em **Novo.**
    
5. Em **Selecionar um Site,** clique no site ao qual a política deve ser aplicada e clique em **OK.**
    
6. Em **Nova Configuração de Qualidade da Experiência,** faça o seguinte:
    
   - Selecione **Habilitar monitoramento de dados de QoE** para ativar o monitoramento.
    
   - Selecione **Habilitar a purgação** de dados de QoE para ativar a purgação.
    
   - Em **Manter QoE por um período máximo (dias),** selecione o número máximo de dias que os registros de QoE devem ser mantidos.
    
7. Clique em **Confirmar**.
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Criando definições de configuração de QoE usando cmdlets do Windows PowerShell

Você pode criar definições de configuração de QoE usando o Windows PowerShell e o New-CsQoEConfiguration cmdlet. Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>Para criar um novo conjunto de definições de configuração de QoE

 Este comando cria uma nova coleção de definições de configuração de QoE aplicadas ao site Redmond:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Para criar um novo conjunto de definições de configuração de QoE onde o monitoramento de QoE está desabilitado

 Como nenhum parâmetro (além do parâmetro obrigatório Identity) foi especificado no comando anterior, o novo conjunto de definições de configurações usará os valores padrões para todas suas propriedades. Para criar configurações que usam valores de propriedade diferentes, basta incluir o parâmetro e o valor de parâmetro adequado. Por exemplo, para criar um conjunto de definições de configuração de Qualidade da Experiência que, por padrão, permite desabilitar a gravação de QoE, use um comando como este:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>Para especificar vários valores de propriedade ao criar uma nova coleção de definições de configuração de QoE

 Você pode vários valores de propriedade incluindo vários parâmetros. Por exemplo, este comando define as novas configurações para manter os dados de QoE por 30 dias e limpar dados antigos às 3:00:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)
  

