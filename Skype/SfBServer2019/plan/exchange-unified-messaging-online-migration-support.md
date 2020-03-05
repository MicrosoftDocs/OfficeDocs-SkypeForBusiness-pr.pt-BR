---
title: Suporte à migração online de Unificação de mensagens do Exchange
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: A Microsoft está desativando o serviço de Unificação de mensagens do Exchange Online (ExchUMO) em 28 de fevereiro de 2020. Este artigo resume o que os clientes afetados devem saber e fazer para planejar sua continuidade de negócios.
ms.openlocfilehash: c39485de1acceef0dc340f039a1586b3e6014522
ms.sourcegitcommit: 5fbb57c5f0692afcb8e65516c63b96814f51ca65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2020
ms.locfileid: "42417616"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Suporte à migração online de Unificação de mensagens do Exchange

> [!IMPORTANT]
> **O serviço de Unificação de mensagens no Exchange Online não tem suporte em 28 de fevereiro de 2020, hora do Pacífico. Todas as contas de caixa postal foram migradas para o serviço de caixa postal na nuvem pela Microsoft. Qualquer tráfego de atendedor automático restante não será monitorado e poderá ser interrompido a qualquer momento.**

Em referência ao [comunicado](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) em 8 de fevereiro de 2019, a Microsoft está desativando o serviço do Exchange Unified Messaging online (ExchUMO) em 28 de fevereiro de 2020. Este artigo oferece um resumo do que os clientes afetados devem saber e fazer para planejar sua continuidade de negócios.
 
O ExchUMO é implantado por clientes de caixa postal, atendedor automático, fila de chamadas e serviços de integração de fax. A Microsoft planeja ajudar os clientes a migrar para serviços de sistema de telefonia que já dão suporte a milhares de clientes no Skype for Business Online e no Microsoft Teams.

A caixa postal é principalmente uma migração orientada pela Microsoft; o envolvimento do administrador e/ou o investimento podem ser necessários para um subconjunto de clientes. O atendedor automático é uma migração orientada pelo administrador; Você precisará recriar as árvores existentes do atendedor automático do ExchUMO no serviço de nuvem do atendedor automático na nuvem. Os clientes que utilizam qualquer um dos recursos do ExchUMO com um PBX de terceiros não serão migrados para os serviços de nuvem do Skype porque não dão suporte a sistemas PBX de terceiros. Um plano de aposentadoria para suporte de terceiros foi anunciado neste [blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853), e os clientes desse modelo de implantação podem migrar seus usuários para uma das plataformas/serviços de comunicações unificadas da Microsoft ou adquirir uma solução de caixa postal e/ou atendedor automático de terceiros para esses usuários. A integração de fax não é suportada nos serviços baseados em nuvem; Os clientes precisarão migrar para uma solução de terceiros.

### <a name="who-is-affected"></a>Quem é afetado?

Os clientes que estiverem consumindo qualquer um dos seguintes recursos do serviço online de Unificação de mensagens do Exchange são afetados:

- Serviço de caixa postal
- Serviço de atendedor automático
- Serviço de fila de chamadas
- Integração de fax

> [!Note]
> Os clientes que usam qualquer um dos servidores do Exchange no local com a Unificação de mensagens não são afetados. 

Saiba mais sobre o impacto da experiência de usuário e de administração no [impacto da experiência do usuário](#user-experience-impact).

## <a name="migration-plan-overview"></a>Visão geral do plano de migração

A Microsoft identificou várias implantações de clientes que estão consumindo recursos do ExchUMO e ajudarão os clientes a migrar com base no plano a seguir. 

|Grupo de clientes |Linha do tempo  |Detalhes  |
|---------|---------|---------|
|Clientes que estão prontos para migrar<br><br>Recursos para migração:<br><ul><li>Caixa postal</ul>   |   Março de maio de 2019  |Exemplos:<ul><li>    Clientes com uso e implantação de caixa postal simples<li>Clientes que têm todos os requisitos estabelecidos para a Microsoft executar a migração<ul>|
|Clientes com pré-requisitos<br><br>Recursos para migração:<br><ul><li>Caixa postal<li>Atendedor automático<li>Fila de chamadas</ul> |  Maio – 2019 de dezembro |Exemplos: <br><ul><li>A configuração híbrida não foi concluída<li>Os números PSTN híbridos não estão configurados</ul>|
|Clientes que exigem o envolvimento do administrador & investimento no cliente<br><br>Recursos para migração:<ul><li>postal<li>Atendedor automático<li>Filas de chamadas<li>Integração de fax</ul>| Em fevereiro de 2020  | Exemplos: <br><ul><li>O serviço ExchUMO é consumido pelo PBX de terceiros<li>Clientes com requisitos de acesso do assinante PSTN<li>Clientes no SFB 2010 (sem suporte)<li>Integração de fax</ul> |

## <a name="voicemail-migration-steps"></a>Etapas de migração de caixa postal

1.  **Ser informado**
 
    Familiarize-se com o [comunicado do blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) e este artigo para planejar uma migração tranqüila para seus usuários. Confira [verificar a caixa postal e as opções do Skype for Business](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) para obter detalhes sobre os recursos de caixa postal do sistema de telefonia.  
 
2.  **Estabelecer uma topologia híbrida do Skype for Business**

    Se você não tiver uma topologia híbrida do Skype for Business estabelecida, será necessário fazer isso para habilitar uma migração tranqüila de seus usuários de caixa postal. Confira [Configurar o Skype for Business híbrido](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) para obter mais detalhes. 

    > [!Note]
    > Você não precisa migrar seus usuários para online para a migração do serviço de caixa postal. No entanto, para usuários locais para aproveitar o serviço de caixa postal do sistema de telefonia, é necessário estabelecer uma topologia híbrida.

3. **Planejar a migração do atendedor automático**
    
    Os administradores podem começar a migrar seus atendedores automáticos do ExchUMO para o atendedor automático na nuvem a qualquer momento. Confira [configurar um atendedor automático na nuvem](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) para obter mais detalhes. A Microsoft continua a fornecer recursos de atendedor automático adicionais que os clientes podem considerar necessários para a migração, os administradores devem avaliar o conjunto de recursos e migrar suas instâncias de atendedor automático de acordo. Para comparação de lista de recursos, consulte a [matriz de recursos dos serviços baseados em nuvem do ExchUMO e do Azure](#exchumo-and-azure-cloud-based-services-feature-matrix).

4. **Planejar a validação e o teste de migração de correio de voz**

    A migração de caixa postal é orientada pela Microsoft. Os administradores não precisam fazer nada, dado que a topologia híbrida de pré-requisito foi estabelecida. A Microsoft realiza a validação e os testes necessários para garantir que a migração de caixa postal dos usuários não seja interrompida. Os administradores são incentivados a executar testes e validação no seu lado. Veja o [plano de teste sugerido e a validação pós-implantação para administradores](#suggested-test-plan-and-post-migration-validation-for-admins) de um plano de teste recomendado. 

    > [!Note]
    > O Lync Server 2010 não é suportado. Se você estiver em uma implantação de servidor 2010, deverá planejar uma atualização de servidor ou considerar a migração de seus usuários para o Microsoft Teams ou o Skype for Business online.  

5. **Monitorar o centro de notificação de administração**

    Procure um aviso no centro de notificação de administração com mais detalhes e linha do tempo em relação à migração dos seus usuários. As notificações são enviadas pelo menos 30 dias antes do período de migração. 

    > [!Note]
    > Se você recebeu uma notificação com a linha do tempo de migração dos seus usuários e deseja adiar sua migração por um motivo crítico para os negócios, é possível fazer isso contatando o suporte da Microsoft. Observe que você não pode adiar a migração além da data de aposentadoria, 28 de fevereiro de 2020. Para clientes que podem ter mais dúvidas, entre em contato com a equipe de conta ou com o suporte da Microsoft. Os clientes que já usam o Office 365 podem enviar um caso de suporte através do portal de administração do Office 365. 

6. **Considere optar por uma migração planejada**

    Você pode optar por uma migração planejada de serviço de caixa postal para o CVM. Antes de optar por, revise os detalhes deste artigo, especialmente as seguintes seções:

    - Etapas de migração (esta seção)
    - ExchUMO e matriz de recursos de serviços baseados em nuvem do Azure
    - Impacto da experiência do usuário

    Ao escolher uma migração gerenciada, você não receberá uma notificação de pré-migração de 30 dias no centro de mensagens do portal de administração do Microsoft 365.
 
    Para aceitar uma migração planejada, envie uma solicitação de email do endereço de email do administrador para [CVM@microsoft.com](mailto:cvm@microsoft.com) com as seguintes informações:

    - Data preferida (terças-feiras): as ondas de migração são executadas a cada terça-feira. Selecione uma data em uma terça-feira que não ultrapasse 12/3/2019.
 
    - ID do locatário: 32 número de caracteres neste formato 0046728c-688a-4472-a38f-098fec60ac6x. Você pode encontrar sua ID de locatário no portal de administração do Microsoft 365 no Azure AD ou usando o seguinte cmdlet do PowerShell:`Get-CsTenant | Select ObjectId`
 
    Você receberá uma confirmação de email quando o locatário for migrado com êxito.

## <a name="auto-attendant-migration-guidelines"></a>Diretrizes de migração do atendedor automático

Os administradores de locatários do Office 365 precisam recriar seus atendedores automáticos online da UM do Exchange no serviço de atendedor automático do Microsoft Cloud e mudar seus números de telefone locais para eles antes de 28 de fevereiro de 2020, que é quando o serviço do Exchange UMO será desativar. Esta é a diretriz recomendada para migrar com êxito e testar novos atendedores automáticos na nuvem. Se você tiver um grande número de atendedores automáticos, poderá usar o [atendedor automático da um do Exchange para os scripts de migração do atendedor](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) automático na nuvem para simplificar a migração em massa de atendedores automáticos.

### <a name="setup"></a>Configuração

É altamente recomendável que você inicie a configuração de seus novos atendedores automáticos antes de evitar problemas de última hora e se familiarizar com a funcionalidade e a experiência do serviço atendedor automático na nuvem. Para atendedores automáticos que exigem um ou mais recursos de lacuna, você pode criar e testar atendedores automáticos quando os recursos de lacuna estão disponíveis para se preparar para a implantação. Para obter mais informações sobre os recursos de espaços, consulte o [Apêndice](#appendix).

1. Use os cmdlets do Exchange UMO para exportar a configuração de atendedores automáticos existentes usando o [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant).  
2. Use o cmdlet [Export-UMprompt](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) no PowerShell do Exchange Online para exportar os arquivos de mídia de saudação (se usado) e convertê-los em formato. mp3.
3. Siga as instruções em [Plan Cloud auto Attendants](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) e [Configure a Cloud auto Attendant](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) para criar atendedores automáticos usando o centro de administração do Microsoft Teams ou o PowerShell.
4. Revise suas saudações se as opções de menu forem alteradas.
5. Configure transferências para seus grupos de resposta usando a solução alternativa "transferência de chamada de atendedor automático para PSTN" na seção [problemas conhecidos](#known-issues) deste artigo.  
6. Teste os novos atendedores automáticos. Para testar, ligue-os internamente ou atribua um número de telefone de teste.  

### <a name="cutover"></a>Substituição

1. Alterne seus números de telefone dos atendedores automáticos do Exchange UMO para os novos atendedores automáticos.
2. Mova o URI SIP do objeto de contato para a conta de recurso.
3. Teste e valide seus atendedores automáticos usando os números de telefone atribuídos recentemente. 

## <a name="appendix"></a>Apêndice

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO e matriz de recursos de serviços baseados em nuvem do Azure

| Serviço | Nível de recurso | Recurso | Observações  | Cloud VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Recursos de serviço| Suporte para PBX de terceiros    | Incluindo todos os recursos fornecidos ao PBX de terceiros, como o MWI (indicador de espera de mensagem) usando mensagens de notificação SIP da UM do Exchange Online | N   | S    |
| VM | Recursos de serviço  | Suporte ao Skype for Business Server   |  | S | S    |
| VM | Recursos de serviço | Suporte ao Microsoft Teams|  | S | N    |
| VM | Recursos de serviço | Descoberta eletrônica e retenção  | Para segurança e conformidade  | S | S    |
| VM | Recursos de serviço | Suporte a regras do Exchange | Para segurança e conformidade  | S | S    |
| VM | Recursos do usuário | Acesso de discagem PSTN  | Acesso ao Assinante  | N | S    |
| VM | Recursos do usuário | PSTN Outlook Voice Access   | Acesso ao Assinante  | N | S    |
| VM | Recursos do usuário | Discar usando um ponto de extremidade autenticado | Chamar o serviço de caixa postal para ouvir mensagens de voz e alterar as configurações de caixa postal| S | S    |
| VM | Recursos do usuário | Configuração do usuário para desabilitar a caixa postal   |  | S | S    |
| VM | Recursos do usuário | Configuração do usuário para alterar a saudação pessoal  |  | S | S    |
| VM | Recursos do usuário | Configuração do usuário para criar uma mensagem de ausência temporária  |  | S | S    |
| VM | Recursos do usuário | Configuração do usuário para alterar o idioma padrão  |  | S | S    |
| VM | Recursos do usuário | Configuração do usuário para substituir a saudação padrão por TTS  |  | S | N    |
| VM | Recursos do usuário | Registrar saudações pessoais (dispositivo autenticado) |  | S | S    |
| VM | Recursos do usuário | Registrar as saudações pessoais (PSTN) — tocar no telefone |  | N | S    |
| VM | Recursos do usuário | Configuração do usuário para desabilitar a transcrição |  | N | S    |
| VM | Recursos do usuário | Transcrição  |  | S | S    |
| VM | Recursos do usuário | Caixa postal Visual em todos os pontos de extremidade   | Com controle de usuário para reproduzir, excluir, indicador de espera de mensagem e status-alternar, em todos os pontos de extremidade suportados  | S | S    |
| VM | Recursos do usuário | Formato de arquivo de áudio MP3 no Outlook    |  | S | S    |
| VM | Recursos do usuário | Controle de execução de velocidade variável |  | S | S    |
| VM | Recursos do usuário | Encaminhar uma caixa postal  | Encaminhar uma caixa postal recebida para outros usuários | S | S    |
| VM | Recursos do usuário | Enviar uma mensagem de voz para um grupo de usuários  |Transmissão de caixa postal   | N | S   |
| VM | Recursos do usuário | Notificação de caixa postal usando SMS    | Os usuários podem receber um SMS quando têm uma nova caixa postal    | N | S    |
| VM | Recursos do usuário | Idiomas de saudação suportados | Detalhes aqui:https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | S | S    |
| VM | Recursos do usuário | Regras de atendimento de chamada |  | S | S    |
| VM | Recursos do usuário | Tocar no telefone (PSTN)-para reproduzir mensagem | Ligar para mim na minha célula para ouvir a mensagem de voz  | N | S    |
| VM | Recursos do usuário | Tocar no telefone (auth)-para reproduzir mensagem | Ligar para mim em meu dispositivo autenticado  | S | S    |
| VM | Recursos do usuário | Caixa de correio compartilhada entre vários usuários |  | S | S    |
| VM | Recursos do chamador  | Experiência de chamadas — caixa postal protegida | O chamador pode escolher uma opção para marcar uma mensagem gravada como protegida| N | S    |
| VM | Recursos do chamador  | Experiência do chamador — caixa postal privada | O chamador pode escolher uma opção para marcar uma mensagem gravada como particular  | N | S    |
| VM | Recursos do chamador  | Detecção de silêncio   |  | N | S    |
| VM | Locatário-recursos de administração | Caixa postal protegida no nível do servidor    | Locatário-o administrador pode configurar uma regra de nível de serviço para marcar a caixa postal de entrada como protegida | S | S    |
| VM | Locatário-recursos de administração | Alterar o limite de tempo de duração da gravação  |     | S | S    |
| VM | Locatário-recursos de administração | Alterar o tempo limite de detecção de silêncio    |  | Não disponível    | S    |
| VM | Locatário-recursos de administração | Alterar o número de falhas de entrada | CVM: embutido em código para 3 | N | S    |
| VM | Locatário-recursos de administração | Alterar o idioma padrão |  | S | S    |
| VM | Locatário-recursos de administração | Desabilitar/habilitar transcrição |  | S | S    |
| VM | Locatário-recursos de administração | Desabilitar/habilitar notificação de chamada perdida |  | N | S    |
| VM | Locatário-recursos de administração | Ajude a Microsoft a melhorar a visualização da caixa postal    |  | S | S    |
| VM | Locatário-recursos de administração | Personalizar mensagem de texto para usuários habilitados|  | Não disponível    | S    |
| VM | Locatário-recursos de administração | Mascaramento de profanação de transcrição|  | S | N    |
| VM | Locatário-recursos de administração | Política de caixa postal    |   | S | S    |
| VM | Locatário-recursos de administração | Administração do portal da Web   |  | CY19   | S    |
| VM | Locatário-recursos de administração | PowerShell   |  | S | S    |
| AA | Recursos de serviço | Suporte AA PBX de terceiros    |  | N | S    |
| AA | Recursos de serviço | Suporte ao Skype for Business Server   |  | S | S    |
| AA | Recursos de serviço | Suporte ao Microsoft Teams|  | S | N    |
| AA | Recursos de serviço | Discar por nome, entrada DTMF    |  | S | S    |
| AA | Recursos de serviço | Discar por nome, entrada de fala  |  | S | S    |
| AA | Recursos de serviço | Suporte a vários idiomas | Detalhes da linguagem aqui:https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | S | S    |
| AA | Recursos de serviço | Transferir para o operador, CQ ou um usuário |  | S | S    |
| AA | Recursos de serviço | Transferir para o número PSTN internamente (RNL)  |  | S | S    |
| AA | Recursos de serviço | Transferir para o número PSTN externamente  |  | Seção Confira os problemas conhecidos abaixo | S    |
| AA | Recursos de serviço | Horário comercial |  | S | S    |
| AA | Recursos de serviço | Opções de menu | Opções do menu IVR  | S | S    |
| AA | Recursos de serviço | Atribuindo um número PSTN de nuvem a AA |  | S | N    |
| AA | Recursos de serviço | Atribuindo um número PSTN local a AA  |  | S | S    |
| AA | Recursos de serviço | Seleção de usuário personalizada  | Permitindo que os chamadores acessem a lista personalizada de usuários da organização| S | S    |
| AA | Recursos de serviço | Tratamento de horas e feriados após  |  | S | S    |
| AA | Recursos de serviço | Saudação personalizada usando texto para fala  |  | S | S    |
| AA | Recursos de serviço | Discagem de ramal   | Atingir um usuário discando sua extensão  | S   | S    |
| AA | Recursos de serviço | Caixa de correio para que os chamadores AA deixem uma mensagem    |  | S   | S    |
| AA | Recursos de serviço | Várias atribuições de números PSTN a um AA|  | S | S    |
| AA | Locatário-recursos de administração | Administração do portal da Web   |  | S | N    |
| AA | Locatário-recursos de administração | Cmdlets do PowerShell  |  | S | S    |
| Fax| Recursos de serviço | Integração de fax|  | N | S    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Plano de teste sugerido e validação após migração para administradores

Para validar que seus usuários foram migrados para a caixa postal na nuvem, deixe uma caixa postal para um usuário e verifique o corpo da mensagem no Outlook.  As mensagens de caixa postal em nuvem têm um rodapé que lê:

**Obrigado por usar a transcrição! Se você não vir uma transcrição acima, isso ocorre porque a qualidade de áudio não era suficientemente clara para transcrever.**

Ao testar a funcionalidade de caixa postal após a migração dos usuários, considere os seguintes cenários:

- Valide o acesso de caixa postal em todos os tipos de ponto de extremidade em sua organização: aplicativos e telefones IP. 
- Validar com os usuários de exemplo que as saudações personalizadas configuradas são reproduzidas aos chamadores.   
- Se sua organização tiver um requisito legal ou de conformidade para desabilitar a transcrição para os usuários, certifique-se de que ele está desabilitado após a migração. Para obter mais detalhes, consulte [set up Cloud Telecaixa de correio](/microsoftteams/set-up-phone-system-voicemail).
- Se você tiver configurado previamente políticas e regras da VM do Exchange, verifique se elas estão em vigor.
- Familiarize-se com os cmdlets do PowerShell do serviço de caixa postal na nuvem para alterar as configurações do usuário.  

### <a name="user-experience-impact"></a>Impacto da experiência do usuário

A seguir está uma visão geral da experiência de migração de caixa postal do usuário final.


|Experiência  |Alteração na experiência do usuário|
|---------|---------|
|Notificação por email | Sem alteração<br>Nenhum email é enviado aos usuários notificando-os sobre ativação/migração da conta de caixa postal. |
|Acesso às mensagens anteriores | Sem alteração<br>Os usuários têm acesso às mensagens de caixa postal anteriores em todos os pontos de extremidade suportados. |
|Recebendo VM no Outlook, aplicativos do SFB| Sem alteração<br>Os usuários continuam a receber mensagens de caixa postal em todos os pontos de extremidade suportados. |
|Transcrição | Metarquivo<br>A transcrição CVM tem uma taxa de precisão muito maior e idiomas com suporte do que o ExchUMO. |
|Configuração do usuário | Nova experiência<br>Os usuários podem alterar suas preferências de um USP (portal de configuração de usuário). Os usuários podem acessar o USP a partir de um hiperlink em seus emails de caixa postal ou do botão Configurações do usuário em seu cliente do SFB; https://aka.ms/vmsettings.   
 |Recursos| Confira a comparação de conjuntos de recursos para obter detalhes. |
|Regras do Outlook para mensagens VM | Sem alteração<br>As regras criadas anteriormente serão aplicadas às mensagens do CVM após a migração.
 |

#### <a name="user-management-and-provisioning-in-cvm"></a>Gerenciamento e provisionamento de usuários no CVM

Novos usuários do Skype for Business serão automaticamente provisionados para a caixa postal em nuvem quando criados. Nenhuma licença ou trabalho de administração adicional é necessária para provisionar novos usuários de caixa postal. Confira [Configurar a caixa postal em nuvem](/microsoftteams/set-up-phone-system-voicemail) para saber mais sobre o gerenciamento de políticas para usuários novos e existentes.

#### <a name="admin-auto-attendant-management-experience"></a>Experiência de gerenciamento de atendedor automático do administrador

Para saber mais sobre atendedores automáticos, consulte [configurar um atendedor automático na nuvem](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).

#### <a name="known-issues"></a>Problemas conhecidos

**Desabilitar o acesso ao Assinante após a migração para evitar a inconsistência de saudação** O acesso ao assinante pode continuar a funcionar para o locatário até que o serviço seja completamente desativado, mesmo depois que todos os seus usuários tenham sido migrados para a caixa postal na nuvem. Para evitar a confusão do usuário e a experiência inconsistente, desabilite o acesso ao Assinante, pois as saudações alteradas após a migração de não terão efeito. Para fazer isso, remova o contato do EXUM para cada linha de acesso do assinante usando Get-CsExUmContact |? {$_. IsSubscriberAccess-EQ $true} | Remove-CsExUmContact 

**Transferência de chamadas de atendedor automático para PSTN** Recomendamos que os clientes configurem temporariamente uma solução alternativa para atender aos requisitos de transferência de uma chamada de atendedor automático para um número externo de PSTN ou para uma instância de RGS. 
 
Um problema foi identificado durante a garantia de qualidade com o recurso transferir para o número PSTN, que não será corrigido no tempo para que os clientes comecem a migrar do serviço do Exchange UMO antes da data de aposentadoria agendada de fevereiro de 28, 2020. Como solução alternativa, os administradores podem transferir chamadores de atendedor automático para um usuário virtual local com uma configuração de encaminhamento de chamada ativa para o número de telefone PSTN desejado ou o número de telefone do RGS. 
 
Experiência esperada
- Os administradores não precisam licenciar o usuário virtual, uma vez que esta é uma solução alternativa 
- Os administradores podem manipular a ID de chamadas que o receptor PSTN verá, atribuindo o número desejado ao usuário virtual ou usando os recursos de manipulação de dígitos de SBC
- Os chamadores PSTN não experimentarão nenhum atraso durante a transferência de chamadas e continuarão a ver a ID de chamadas do atendedor automático após a transferência ter sido bem-sucedida  

**Caixa de correio compartilhada:** Uma caixa de correio compartilhada que é configurada usando o Exchange UM online continuará recebendo mensagens após a migração para o CVM, e continuará a ser acessível aos usuários via Outlook. No entanto, o acesso à alteração das mensagens de saudação dessas caixas de correio não estará disponível após a migração para o CVM. Clientes com caixas de correio compartilhadas que são usadas para capturar chamadores de atendedor automático devem utilizar os recursos de caixa de correio compartilhados de atendedores automáticos e filas de chamada depois de lançado (ETA outubro de 2019).
  
**Atualização para o banner do teams no cliente do SFB:** O serviço CVM é baseado na infraestrutura do Microsoft Teams; chamadas para o cliente do Skype for Business podem fazer com que uma faixa de informações seja exibida no cliente que diz: "username não está usando o Skype for Business. Para uma experiência mais rica, alterne para o Microsoft Teams ou inicie uma reunião do Skype. "
Certifique-se de atualizar o cliente Skype for Business de seus usuários para a atualização mais recente do cliente do C2R para evitar que essa faixa seja exibida.
  
**Configure seu correio de voz para o OWA:** Clicar em "Configurar caixa postal" do cliente continuará a usar os clientes do Skype for Business Server 2015/2013 para a página do portal do Office Web Access (OWA) após a migração para o CVM. Todas as configurações foram removidas da guia caixa postal no OWA e uma faixa será exibida com um link de redirecionamento para levar os usuários ao portal de configurações de usuário do CVM.
 
**Alterar acesso móvel de saudação:** O acesso ao Assinante PSTN não é suportado no CVM. Para usuários que precisam alterar a saudação remotamente, uma opção de menu "alterar sua saudação" é adicionada ao serviço IVR de caixa postal para clientes móveis. Os usuários podem chamar esse serviço pressionando e segurando a chave "1" no painel de discagem do cliente móvel.
