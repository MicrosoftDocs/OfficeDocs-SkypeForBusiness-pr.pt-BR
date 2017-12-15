---
title: "Obtendo números telefônicos de serviço do Skype for Business"
ms.author: tonysmit
author: tonysmit
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734

description: "Além de obter os números telefônicos para usuários individuais do Office 365, também é possível procurar e adquirir números de discagem gratuita ou não para serviços como conferência discada (para pontes de conferências) e atendedores automáticos, que são chamados de números de serviço. Os números telefônicos de serviço têm uma capacidade de chamada simultânea maior do que números de usuários ou assinantes. Por exemplo, um número de serviço pode lidar com centenas de chamadas simultaneamente, ao passo que um número de usuário só pode trabalhar com algumas chamadas de forma simultânea."
---

# Obtendo números telefônicos de serviço do Skype for Business

Além de obter os números telefônicos para usuários individuais do Office 365, também é possível procurar e adquirir números de discagem gratuita ou não para serviços como conferência discada (para pontes de conferências) e atendedores automáticos, que são chamados de números de serviço. Os números telefônicos de serviço têm uma capacidade de chamada simultânea maior do que números de usuários ou assinantes. Por exemplo, um número de serviço pode lidar com centenas de chamadas simultaneamente, ao passo que um número de usuário só pode trabalhar com algumas chamadas de forma simultânea.
  
> [!IMPORTANT]
> O consumo PSTN deve ser definido primeiro, a fim de obter números de discagem gratuitos. 
  
Há duas maneiras de conseguir números de serviço para que você possa usá-los com o Skype for Business: 
  
- Obtenha novos números do Office 365 Skype for Business.
    
- Fazer a portabilidade ou transferir os números existentes de seu provedor de serviços ou de sua operadora de telefonia.
    
    > [!NOTE]
    > Ao transferir seus números de serviço, é altamente recomendável que você entre em contato com o [Contatar o suporte do Office 365 para empresas - Ajuda para Administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) para garantir que a maior capacidade de chamadas simultâneas seja considerada e configurada corretamente.
  
## Obtenha novos números de serviço

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. Na navegação à esquerda, vá para **Voz** > **Números de serviço** > **Adicionar** e clique em **Novos números de serviço**.
    
    **IMPORTANTE**: para ver a opção **Voz** na navegação à esquerda no Centro de Administração do Skype for Business, você deve comprar pelo menos uma **licença Enterprise E5**, uma licença de complemento de **Sistema Telefônico** ou uma licença de complemento de **Audioconferência**.
    
4. Na página **Adicionar novos números de serviço**, use os menus suspensos para escolher:
    
  - **País/Região**
    
  - **Estado/Região**
    
  - **Cidade**
    
5.  Em **Quantidade**, digite a quantidade de números de telefone desejados para a organização e clique em **Adicionar** para criar uma reserva. Você tem 10 minutos para selecionar os números de telefone. Se levar mais de 10 minutos, os números de telefone retornarão ao pool de números de telefone.
    
    > [!NOTE]
    > Você pode ver a quantidade de números de telefone com base no número de licenças listadas ao lado de **Número total de usuários que você pode adquirir**. 
  
6. Clique em **Mostrar números** para ver a lista completa de números de telefone. Isso é útil se você não quiser selecionar um número de telefone específico na lista.
    
7. Selecione os números de telefone desejados e clique em **Adquirir números**.
    
### Atribuir números de serviço

Depois que você obtiver os números de serviço, eles poderão ser atribuídos a uma ponte de conferência discada. Para isso, veja [Alterar a chamada Tarifada ou números gratuitos de Chamada Tarifada em sua ponte de conferência de áudio](../audio-conferencing-in-office-365/change-the-toll-or-toll-free-numbers-on-your-audio-conferencing-bridge.md).
  
### Fazer a portabilidade ou transfira números de serviço existentes

Se quiser transferir números de serviço do seu provedor ou operador de serviços atual, você precisará enviar manualmente um pedido de portabilidade para a Microsoft. Você tem que enviar pedidos de portabilidade separados para cada tipo de número de serviço (discagem paga ou discagem gratuita) que transferir usando uma Carta de Autorização (LOA). Na LOA (Carta de Autorização), você deve selecionar o tipo correto de número de serviço. Ao contatar o suporte da Microsoft, especifique que está transferindo um número de serviço ( *e não um número de usuário ou de assinante*  ). Caso contrário, a capacidade de chamadas simultâneas poderá não ser suficiente para lidar com os volumes de chamada. Se você deseja saber mais sobre o envio de solicitações de pedido de portabilidade, veja[Enviar uma solicitação de atendimento ao cliente manualmente](../what-are-calling-plans-in-office-365/manually-submit-a-custom-service-request.md)
  
## Expanda para ver quantos números de telefone você pode obter.

Ao procurar e obter números de telefone para a sua organização, é possível obter mais números de telefone do que a quantidade de licenças atribuídas. Mas isso depende dos tipos de números de telefone e de licenças que você comprou e atribuiu.
  
Você pode ver o números de telefones que pode obter na página **Números de telefone** no Centro de administração do Skype for Business ou você pode executar o cmdlet[Get-CsOnlineTelephoneNumberAvailableCount](https://technet.microsoft.com/en-us/library/mt634605.aspx). 
  
> [!IMPORTANT]
> Os limites abaixo não incluem números de telefone que você fez portabilidade ou transferiu para a Microsoft. 
  
||||
|:-----|:-----|:-----|
|**Para este tipo de número de telefone** <br/> |**Como calcular o total de números de telefone?** <br/> |**Veja um exemplo** <br/> |
|Número de usuário (assinante)  <br/> |A quantidade de números de telefone é igual ao número total de licenças do plano de Chamadas de Voz  *Domésticas + Domésticas e Internacionais*  multiplicado por 1,1 + 10 números de telefone adicionais que são fornecidos. <br/> |Se você tem no total 50 usuários com os planos de Chamada de Voz Domésticas e Domésticas e Internacionais, pode adquirir **65** números de telefone **(50 x 1.1 + 10)**. <br/> |
|Número do serviço de chamada tarifada  <br/> | A quantidade de números de telefone é igual ao número total de licenças de *Cloud PBX + Conferência PSTN*  e segue esta regra: <br/>  Se houver **1 a 25 licenças**, serão fornecidos **5** números de telefone. <br/>  Se houver **26 a 49 licenças**, serão fornecidos **10** números de telefone. <br/>  Se houver **50 a 99 licenças**, serão fornecidos **20** números de telefone. <br/>  Se houver **100 a 149 licenças**, serão fornecidos **30** números de telefone. <br/>  Se houver **150 a 199 licenças**, serão fornecidos **40** números de telefone. <br/>  Se houver **200 a 499 licenças**, serão fornecidos **65** números de telefone. <br/>  Se houver **500 a 749 licenças**, serão fornecidos **90** números de telefone. <br/>  Se houver **750 a 999 licenças**, serão fornecidos **110** números de telefone. <br/>  Se houver **1.000 a 1.249 licenças**, serão fornecidos **125** números de telefone. <br/>  Se houver **1.250 a 1.499 licenças**, serão fornecidos **135** números de telefone. <br/>  Se houver **1.500 a 1.999 licenças**, serão fornecidos **160** números de telefone. <br/>  Se houver **2.000 a 2.999 licenças**, serão fornecidos **210** números de telefone. <br/>  Se houver **3.000 a 6.999 licenças**, serão fornecidos **420** números de telefone. <br/>  Se houver **7.000 a 9.999 licenças**, serão fornecidos **500** números de telefone.%+% <br/>  Se houver **10.000 a 14.999 licenças**, serão fornecidos **600** números de telefone. <br/>  Se houver **15.000 a 19.999 licenças**, serão fornecidos **700** números de telefone.%+% <br/>  Se houver **20.000 a 49.999 licenças**, serão fornecidos **1.000** números de telefone. <br/>  Se houver **mais de 50.000 licenças**, serão fornecidos **1.500** números de telefone. <br/> |Se você tiver um total de **51** licenças de Cloud PBX e Conferência PSTN, poderá obter **20** números do serviço de chamada tarifada. <br/> |
| Número do serviço de chamada gratuita <br/> | A quantidade de números de telefone é igual ao número total de licenças de *Cloud PBX + Conferência PSTN*  e segue esta regra: <br/>  Se houver **1 a 25 licenças**, serão fornecidos **5** números de telefone. <br/>  Se houver **26 a 49 licenças**, serão fornecidos **10** números de telefone. <br/>  Se houver **50 a 99 licenças**, serão fornecidos **20** números de telefone. <br/>  Se houver **100 a 149 licenças**, serão fornecidos **30** números de telefone. <br/>  Se houver **150 a 199 licenças**, serão fornecidos **40** números de telefone. <br/>  Se houver **200 a 499 licenças**, serão fornecidos **65** números de telefone. <br/>  Se houver **500 a 749 licenças**, serão fornecidos **90** números de telefone. <br/>  Se houver **750 a 999 licenças**, serão fornecidos **110** números de telefone. <br/>  Se houver **1.000 a 1.249 licenças**, serão fornecidos **125** números de telefone. <br/>  Se houver **1.250 a 1.499 licenças**, serão fornecidos **135** números de telefone. <br/>  Se houver **1.500 a 1.999 licenças**, serão fornecidos **160** números de telefone. <br/>  Se houver **2.000 a 2.999 licenças**, serão fornecidos **210** números de telefone. <br/>  Se houver **3.000 a 6.999 licenças**, serão fornecidos **420** números de telefone. <br/>  Se houver **7.000 a 9.999 licenças**, serão fornecidos **500** números de telefone.%+% <br/>  Se houver **10.000 a 14.999 licenças**, serão fornecidos **600** números de telefone. <br/>  Se houver **15.000 a 19.999 licenças**, serão fornecidos **700** números de telefone.%+% <br/>  Se houver **20.000 a 49.999 licenças**, serão fornecidos **1.000** números de telefone. <br/>  Se houver **mais de 50.000 licenças**, serão fornecidos **1.500** números de telefone. <br/> |Se você tiver um total de **1.001** licenças de Cloud PBX e Conferência PSTN, poderá obter **125** números do serviço de chamada gratuita. <br/> > [!IMPORTANT]> A [Configurar comunicações créditos para sua organização](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md) é necessária para reservar e usar números de telefone de chamada gratuita.          |
   
> [!NOTE]
> Se precisar de mais números de telefone, consulte [Contatar o suporte do Office 365 para empresas - Ajuda para Administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). 
  
## Tópicos Relacionados

[Termos e condições para chamadas de emergência](../what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions.md)
  
[Áudio período discar complementar de conferência](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  

