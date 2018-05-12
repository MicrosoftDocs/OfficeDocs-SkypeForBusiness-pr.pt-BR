---
title: Configurar telefones de área comum
description: Conheça as etapas de implantação para obter o firmware correto, atualizá-la, se necessário, atribuir licenças e definir configurações para telefones de área comum.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
ms.openlocfilehash: b7e3a20bc08af0900a64ceacc817bdeaffd5f326
ms.sourcegitcommit: febd51fd7988602a8c9839e4e9872ae8f5d77c63
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2018
---
# <a name="set-up-common-area-phones"></a>Configurar telefones de área comum

Um telefone de área comum ou COBRIR, é geralmente colocada em uma área compartilhada e não associado a um usuário individual. Por exemplo, um telefone de área de recepção, porta telefone ou sala de reunião telefone, maiusculas são configuradas como dispositivos em vez de usuários e entrar automaticamente à rede. Nas etapas abaixo, podemos ajudá-lo a configurar uma conta para o sistema de telefone da Microsoft com planos de chamada e, em seguida, implantar uma Capitular.

## <a name="prerequisites-for-common-area-phones"></a>Pré-requisitos para telefones de área comum

Confirme que você tenha o seguinte:

-   - Adquirido SKU do telefone de área comum 
-   - Firmware atualizado (consulte Firmware suportados neste tópico:https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)
-   - Aprovado telefones (exibir a lista em:            
        https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)

## <a name="check-the-firmware-for-your-phone"></a>Verifique o firmware para o seu telefone
- **Telefones Polycom VVX**, vá para **Configurações** > **Status** > **Plataforma** > **Aplicativo** > **Principal**.
- **Telefones Yealink**, vá para **Status** na tela do telefone principal.
- **AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen. 
- **Telefones Lync Phone Edition (LPE)**, vá para **Menu** > **Informações do Sistema** na tela inicial.

As atualizações de firmware são gerenciadas pelo Serviço do Skype for Business. Todo firmware de telefone certificado pelo Skype for Business é carregado para o servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão. 

Dependendo do tempo de inatividade no telefone e nos intervalos de sondagem, os telefones baixarão e instalarão automaticamente os builds certificados mais recentes. Você pode desabilitar as configurações de atualização de dispositivo usando o cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) e definindo o parâmetro _EnableDeviceUpdate_ para `false`.

## <a name="create-cap"></a>Criar COBRIR
Você pode criar o COBRIR definindo as configurações antes de configurar o telefone físico.

#### <a name="purchase-the-common-area-phone-sku"></a>Adquira o telefone de área comum SKU. 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a>Configurar o telefone de área comum<!-- this section could use a screen shot-->

**Criar um usuário** 
1. Atribuir um telefone de área comum SKU
2. Atribua chamar planejar (se estiver usando o sistema de telefone da Microsoft com planos de chamada). 
3. Atribuir um número de telefone disponíveis no Skype para Business Admin Center, ou solicitar um novo número de telefone.

**Criar um novo usuário**

1. No painel de provisionamento, você tem uma opção para digitar um nome e sobrenome (por exemplo, Main de recepção).
2. Insira um nome para exibição (obrigatório), por exemplo, "Main recepção."
3. Insira um nome de usuário (obrigatório), por exemplo "MainReception" @"domínio" (nome de empresa ou enterprise)
4. Insira o local (país).

**Atribuir um telefone de área comum SKU** No Centro de administração do Office 365, vá para **faturamento > Serviços de compra** e adicione o **Telefone de área comum**

**Atribuir o plano de chamada no COBRIR SKU**

1. Selecione uma chamada planeja habilitar o telefone. 
2. Adicione o limite para permitir que o sistema telefônico e Skype para negócios Online plano 2 na SKU COBRIR. <!-- odd order for step -->

**Atribuir um número de telefone**
1. Verificar números de telefone disponíveis em **voz > números de telefone**.
2. Selecione um número na lista disponível do número de números de telefone.
3. Confirme sua seleção selecionando os **Números de telefone**e **voz** .

    >[!NOTE]
    Usuários de voz mostram somente se tiverem a licença do sistema telefônico aplicada, embora o mesmo depois de aplicar, poderá demorar para ser atualizada. Reabrir um dia Skype para Business Admin center ajuda.
    
## <a name="configure-phone"></a>Configurar o telefone

**Preparar os telefones físicos**

Seu telefone escolhido precisa ter o modo de telefone de área comum. 

***Telefone de Polycom VVX de exemplo***

Habilite o modo de telefone de área comum para o VVX Polycom seguindo estas etapas:
1. No seu navegador, use a interface da web para habilitar o modo de COBRIR o VVX
2. Vá para **configuração** e no Skype para a opção de configuração de negócios, selecione o **Telefone de área comum**.
3. Clique em **Sim** para salvar as suas definições de configuração.

Agora que o modo de telefone COBRIR estiver habilitado, configure o telefone usando a exibição do telefone. A exibição deve mostrar "CaAP está habilitado".

1. Clique em **configurações**.
2. Selecione **Avançado**.
3. Insira a senha.
4. Nas configurações de administração, selecione **Configurações de telefone de área comum**.
5. Habilite **COBRIR** e **modo COBRIR Admin**.
6. Clique em **Salvar o arquivo Config**.

Seu telefone está pronto para ser provisionados, o qual você vai fazer quando você entrar na tela inicial.

1. Entrar, selecionando **configurações** > **recursos** > **Skype for Business.**
2. Selecione **As credenciais do usuário**e, em seguida, selecione **entrar na web (COBRIR)** para gerar um código..
3. Vá para o portal do provisionamento em http://aka.ms/skypecape entrar como **admin**.
4. Insira o nome de exibição (por exemplo, Main recepção) para exibir seu limite.

>[!NOTE]
Se "Pesquisa para telefones de área comum apenas" estiver marcada, desmarque a caixa de seleção e pesquisar novamente.

5. Na janela de código de emparelhamento, insira o código exibido no telefone e clique em **fornecimento**.

Após essa última etapa, o telefone deve entrar automaticamente.

Saiba mais sobre os telefones disponíveis em [Implantando Skype para telefones Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).


