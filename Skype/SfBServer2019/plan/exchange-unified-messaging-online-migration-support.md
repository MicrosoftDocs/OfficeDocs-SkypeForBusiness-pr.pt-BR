---
title: Suporte à migração da Unificação de Mensagens do Exchange Online
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: A Microsoft está desativando o serviço online de Unificação de mensagens do Exchange (ExchUMO) em fevereiro de 2020. Este artigo resume o que os clientes afetados devem saber e fazer para planejar sua continuidade de negócios.
ms.openlocfilehash: d959a4b3ff04a8f2de9182d0df9cc5f63941a5dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280847"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Suporte à migração da Unificação de Mensagens do Exchange Online  

Em referência ao [anúncio](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) em 8 de fevereiro de 2019, a Microsoft está desativando o serviço do Exchange Unified Messaging online (ExchUMO) até 2020 de fevereiro. Este artigo oferece um resumo do que os clientes afetados devem saber e fazer para planejar sua continuidade de negócios. 
 
O ExchUMO é implantado por clientes para correio de voz, atendedor automático e/ou serviços de integração de fax. A Microsoft planeja ajudar esses clientes a migrarem para seus serviços baseados em nuvem que dão suporte a milhares de clientes que já têm o Skype for Business Online e o Microsoft Teams. 

O correio de voz é basicamente uma migração orientada pela Microsoft; o envolvimento do administrador e/ou o investimento podem ser necessários para um subconjunto de clientes. O atendedor automático é uma migração orientada por administradores; Você precisará recriar as árvores de atendedor automático do ExchUMO no serviço de nuvem do atendedor automático na nuvem. Os clientes que estiverem consumindo qualquer um dos recursos do ExchUMO com um PBX de terceiros não serão migrados para os serviços de nuvem da Skype porque não são compatíveis com sistemas PBX de terceiros. Um plano de aposentadoria para suporte a terceiros foi anunciado no ano passado neste [blog](https://blogs.technet.microsoft.com/exchange/2017/07/18/discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging
), e os clientes neste modelo de implantação podem migrar os usuários para um dos serviços/plataformas de comunicação unificada da Microsoft ou adquirir um correio de voz de terceiros e/ou solução de atendedor automático para estes usuários. Não há suporte para a integração de fax nos serviços baseados em nuvem; Os clientes precisarão migrar para uma solução de terceiros. 

### <a name="who-is-affected"></a>Quem é afetado?

Os clientes que estão consumindo qualquer um dos seguintes recursos do serviço online de Unificação de mensagens do Exchange são afetados:

1. Serviço de correio de voz 
2. Serviço de atendedor automático 
3. Integração de fax 

> [!Note]
> Os clientes que usam qualquer um dos servidores Exchange no local com Unificação de mensagens não são afetados. 

Saiba mais sobre o impacto da experiência do usuário e do administrador no [impacto da experiência do usuário](#user-experience-impact).

## <a name="migration-plan-overview"></a>Visão geral do plano de migração

A Microsoft identificou várias implantações de clientes que estão consumindo recursos do ExchUMO e ajudará os clientes a migrar com base no plano a seguir. 


|Grupo de clientes |Cronológica  |Detalhes  |
|---------|---------|---------|
|Clientes que estão prontos para migrar<br><br>Recursos a serem migrados:<br><ul><li>Caixa postal</ul>   |   Março – maio de 2019  |Exemplos<ul><li>    Clientes com implantação e uso simples de correio de voz<li>Clientes que têm todos os requisitos estabelecidos pela Microsoft para executar a migração<ul>|
|Clientes com pré-requisitos<br><br>Recursos a serem migrados:<br><ul><li>Caixa postal<li>Atendedor automático</ul> |  Maio – Dezembro de 2019 |Exemplos <br><ul><li>A configuração híbrida não é estabelecida/concluída<li>Os números PSTN híbridos não estão configurados</ul>|
|Clientes que exigem envolvimento do administrador & investimento do cliente<br><br>Recursos a serem migrados:<ul><li>caixa<li>Atendedor automático<li>Integração de fax</ul>| Até fevereiro de 2020  | Exemplos <br><ul><li>O serviço ExchUMO é consumido pelo PBX com terceiros<li>Clientes com requisitos de acesso do assinante PSTN<li>Clientes no SFB 2010 (não suportados)<li>Integração de fax</ul> |

## <a name="migration-steps"></a>Etapas de migração

1.  **Seja informado**
 
    Familiarize-se com o [anúncio do blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) e este artigo para planejar uma migração tranqüila para seus usuários. Consulte [verificar a caixa postal e as opções do Skype for Business](https://support.office.com/en-us/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) para obter detalhes sobre os recursos de correio de voz na nuvem.  
 

2.  **Estabelecer uma topologia híbrida do Skype for Business**

    Se você não tiver uma topologia híbrida do Skype for Business estabelecida, será necessário fazer isso para habilitar uma migração tranqüila dos usuários de correio de voz. Consulte [Configurar o Skype for Business híbrido](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) para obter mais detalhes. 

    > [!Note]
    > Você não precisa migrar os usuários para online para a migração do serviço de correio de voz. No entanto, para que os usuários locais aproveitem o serviço de correio de voz baseado em nuvem, é preciso estabelecer uma topologia híbrida.

3. **Planejar a migração do atendedor automático**
    
    Os administradores podem começar a migrar atendedores automáticos do ExchUMO para o atendedor automático da nuvem a qualquer momento. Consulte [configurar um atendedor automático na nuvem](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) para obter mais detalhes. A Microsoft planeja fornecer recursos adicionais de atendedor automático que os clientes consideram essenciais para a migração de março de 2019. Os administradores devem avaliar o conjunto de recursos e migrar suas instâncias de atendedor automático de acordo com isso. Para comparação de lista de recursos, consulte a [matriz de recursos de serviços baseados em nuvem do ExchUMO e do Azure](#exchumo-and-azure-cloud-based-services-feature-matrix).

4. **Planejar a validação e os testes de correio de voz após a migração**

    A migração de correio de voz é orientada pela Microsoft; Os administradores não precisam fazer nada, uma vez que a topologia híbrida pré-requisito é estabelecida. A Microsoft executará a validação e os testes necessários para garantir que a migração de correio de voz dos usuários não seja interrompida; no entanto, os administradores são incentivados a executar testes e validação em seus lados.  Consulte [plano de teste sugerido e validação pós-implantação para administradores](#suggested-test-plan-and-post-migration-validation-for-admins) para um plano de teste recomendado. 

    > [!Note]
    > Não há suporte para Lync Server 2010. Se você estiver em uma implantação do servidor do 2010, planeje uma atualização do servidor ou considere a migração de seus usuários para o Microsoft Teams ou o Skype for Business online.  

5. **Monitorar o centro de notificações de administração**

    Procure uma notificação no centro de notificações de administração com detalhes adicionais e linha do tempo sobre a migração de correio de voz dos usuários. As notificações serão enviadas pelo menos 30 dias antes do período de migração. 

    > [!Note]
    > Se você recebeu uma notificação com a linha do tempo de migração dos seus usuários e gostaria de adiar a migração para um motivo crítico para os negócios, você pode fazer isso entrando em contato com o suporte da Microsoft. Observe que não é possível adiar a migração para além da data de aposentadoria, de fevereiro de 2020. Para clientes que podem ter mais dúvidas, entre em contato com a equipe da sua conta ou com o suporte da Microsoft. Os clientes que já usam o Office 365 podem enviar um caso de suporte por meio do portal de administração do Office 365. 

6. **Considere a possibilidade de optar pelo início de maio de 2019**

    Você pode optar por fazer uma migração do serviço de correio de voz antecipada de maio de 2019 (se você não tiver recebido uma notificação de migração) para alinhar a migração com uma anuidade de licenças ou férias de equipe de administração ou para evitar períodos críticos para os negócios. Detalhes sobre o processo de consentimento serão atualizados neste artigo antes de 2019.  

## <a name="appendix"></a>Anexo

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matriz de recursos de serviços baseados em nuvem do ExchUMO e do Azure 




| Atender | Nível do recurso | Recurso | Observações  | Cloud VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VIRTUAIS  | Recursos do serviço| Oferecer suporte a PBX de terceiros    | Incluir todos os recursos fornecidos ao PBX de terceiros, como o MWI (Message Waiting Indicator) usando mensagens de notificação SIP do Exchange UM online | N   | Y    |
| VIRTUAIS | Recursos do serviço  | Suporte para o Skype for Business Server   |  | Y | S    |
| VIRTUAIS | Recursos do serviço | Suporte ao Microsoft Teams|  | Y | N    |
| VIRTUAIS | Recursos do serviço | Descoberta eletrônica e retenção  | Para segurança e conformidade  | S | S    |
| VIRTUAIS | Recursos do serviço | Suporte a regras do Exchange | Para segurança e conformidade  | S | S    |
| VIRTUAIS | Recursos do usuário | Acesso de discagem PSTN  | Acesso do assinante  | N | Y    |
| VIRTUAIS | Recursos do usuário | Acesso de voz do Outlook em PSTN   | Acesso do assinante  | N | Y    |
| VIRTUAIS | Recursos do usuário | Discagem usando um ponto de extremidade autenticado | Como chamar o serviço de correio de voz para ouvir mensagens de voz e alterar as configurações de correio de voz| S | S    |
| VIRTUAIS | Recursos do usuário | Configuração do usuário para desativar o correio de voz   |  | S | S    |
| VIRTUAIS | Recursos do usuário | Configuração do usuário para alterar a saudação pessoal  |  | S | S    |
| VIRTUAIS | Recursos do usuário | Configuração do usuário para criar uma saudação OOF  |  | S | S    |
| VIRTUAIS | Recursos do usuário | Configuração do usuário para alterar o idioma padrão  |  | S | S    |
| VIRTUAIS | Recursos do usuário | Configuração do usuário para substituir a saudação padrão por TTS  |  | Y | N    |
| VIRTUAIS | Recursos do usuário | Gravar saudações pessoais (dispositivo autenticado) |  | S | S    |
| VIRTUAIS | Recursos do usuário | Gravar saudações pessoais (PSTN)-tocar no telefone |  | N | Y    |
| VIRTUAIS | Recursos do usuário | Configuração do usuário para desabilitar a transcrição |  | N | Y    |
| VIRTUAIS | Recursos do usuário | Transcrição  |  | S | S    |
| VIRTUAIS | Recursos do usuário | Caixa postal Visual em todos os pontos de extremidade   | Com o controle de usuário para reproduzir, excluir, indicador de mensagem aguardando e status-alternar, em todos os pontos de extremidade compatíveis  | S | S    |
| VIRTUAIS | Recursos do usuário | Formato de arquivo de áudio MP3 no Outlook    |  | S | S    |
| VIRTUAIS | Recursos do usuário | Controle de reprodução de velocidade variável |  | S | S    |
| VIRTUAIS | Recursos do usuário | Encaminhar um correio de voz  | Encaminhar um correio de voz recebido para outros usuários | Y | S    |
| VIRTUAIS | Recursos do usuário | Enviar uma mensagem de voz para um grupo de usuários  |Transmissão de correio de voz   | N | Y   |
| VIRTUAIS | Recursos do usuário | Notificação de correio de voz usando SMS    | Os usuários podem receber SMS quando tiverem um novo correio de voz    | N | Y    |
| VIRTUAIS | Recursos do usuário | Idiomas de saudação suportados | Detalhes aqui:https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | Y | S    |
| VIRTUAIS | Recursos do usuário | Regras de atendimento de chamada |  | Y | S    |
| VIRTUAIS | Recursos do usuário | Executar no telefone (PSTN)-para reproduzir mensagem | Ligar para mim na minha célula para ouvir a mensagem de voz  | N | Y    |
| VIRTUAIS | Recursos do usuário | Reproduzir no telefone (auth)-para reproduzir mensagem | Ligar para mim no meu dispositivo autenticado  | Y | S    |
| VIRTUAIS | Recursos do usuário | Caixa de correio compartilhada entre vários usuários |  | Y | S    |
| VIRTUAIS | Recursos do chamador  | Experiência de chamadas-correio de voz protegido | O chamador pode escolher uma opção para marcar uma mensagem gravada como protegida| N | Y    |
| VIRTUAIS | Recursos do chamador  | Experiência de chamadas-correio de voz particular | O chamador pode escolher uma opção para marcar uma mensagem gravada como particular  | N | Y    |
| VIRTUAIS | Recursos do chamador  | Detecção de silêncio   |  | N | Y    |
| VIRTUAIS | Locatário-recursos de administração | Correio de voz protegido no nível do servidor    | Locatário-o administrador pode configurar uma regra de nível de serviço para marcar o correio de voz recebido como protegido | Y | S    |
| VIRTUAIS | Locatário-recursos de administração | Alterar o limite de tempo de duração da gravação  | CVM embutido em 5 minutos    | N | Y    |
| VIRTUAIS | Locatário-recursos de administração | Alterar o tempo limite de detecção de silêncio    |  | N/D    | Y    |
| VIRTUAIS | Locatário-recursos de administração | Alterar o número de falhas de entrada | CVM: embutido em código para 3 | N | Y    |
| VIRTUAIS | Locatário-recursos de administração | Alterar o idioma padrão |  | Y | S    |
| VIRTUAIS | Locatário-recursos de administração | Desabilitar/habilitar transcrição |  | Y | S    |
| VIRTUAIS | Locatário-recursos de administração | Desabilitar/habilitar a notificação de chamada perdida |  | N | Y    |
| VIRTUAIS | Locatário-recursos de administração | Ajude a Microsoft a melhorar a visualização da caixa postal    |  | S | S    |
| VIRTUAIS | Locatário-recursos de administração | Personalizar mensagem de texto para usuários habilitados|  | N/D    | Y    |
| VIRTUAIS | Locatário-recursos de administração | Mascaramento de obscenidades da transcrição|  | Y | N    |
| VIRTUAIS | Locatário-recursos de administração | Política de correio de voz    |   | S | S    |
| VIRTUAIS | Locatário-recursos de administração | Administração do portal da Web   |  | CY19   | Y    |
| VIRTUAIS | Locatário-recursos de administração | ™   |  | S | S    |
| Altere | Recursos do serviço | AA compatível com PBX de terceiros    |  | N | Y    |
| Altere | Recursos do serviço | Suporte para o Skype for Business Server   |  | S | S    |
| Altere | Recursos do serviço | Suporte ao Microsoft Teams|  | Y | N    |
| Altere | Recursos do serviço | Discar por nome, entrada DTMF    |  | S | S    |
| Altere | Recursos do serviço | Discar por nome, entrada de fala  |  | S | S    |
| Altere | Recursos do serviço | Suporte a vários idiomas | Detalhes da linguagem aqui:https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | S | S    |
| Altere | Recursos do serviço | Transferir para o Operator, o CQ ou um usuário |  | S | S    |
| Altere | Recursos do serviço | Transferir para o número PSTN internamente (RNL)  |  | S | S    |
| Altere | Recursos do serviço | Transferir para o número PSTN externamente  |  | Q2CY19 | Y    |
| Altere | Recursos do serviço | Horário comercial |  | S | S    |
| Altere | Recursos do serviço | Opções do menu | Opções do menu IVR  | S | S    |
| Altere | Recursos do serviço | Atribuindo um número PSTN à nuvem para AA |  | Y | N    |
| Altere | Recursos do serviço | Atribuindo um número PSTN local a AA  |  | S | S    |
| Altere | Recursos do serviço | Seleção de usuário personalizada  | Como habilitar os chamadores para acessar a lista personalizada de usuários da organização| S | S    |
| Altere | Recursos do serviço | Tratamento de horas extras e feriados  |  | S | S    |
| Altere | Recursos do serviço | Saudação personalizada usando texto para fala  |  | S | S    |
| Altere | Recursos do serviço | Discagem de extensão   | Como alcançar um usuário ao discar a extensão dele  | CY19   | Y    |
| Altere | Recursos do serviço | Caixa de correio para chamadores AA para deixar uma mensagem    |  | CY19   | Y    |
| Altere | Recursos do serviço | Atribuição de vários números PSTN a um AA|  | S | S    |
| Altere | Locatário-recursos de administração | Administração do portal da Web   |  | Y | N    |
| Altere | Locatário-recursos de administração | Cmdlets do PowerShell  |  | S | S    |
| Fax| Recursos do serviço | Integração de fax|  | N | Y    |



### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Plano de teste sugerido e validação após a migração para administradores

Ao testar a funcionalidade de correio de voz após a migração dos usuários, considere os seguintes cenários:

- Valide o acesso ao correio de voz entre todos os tipos de ponto de extremidade em sua organização: aplicativos e telefones IP. 
- Valide com os usuários de exemplo que as saudações personalizadas configuradas são jogadas aos chamadores.   
- Se a sua organização tiver uma exigência legal ou de conformidade para desativar a transcrição para os usuários, verifique se ela está desabilitada após a migração. Para obter mais detalhes, consulte [Configurar correio de voz na nuvem](/microsoftteams/set-up-phone-system-voicemail).
- Se você configurou anteriormente políticas e políticas de VM do Exchange, certifique-se de que elas estejam em vigor.
- Familiarize-se com os cmdlets do PowerShell do serviço de correio de voz na nuvem para alterar configurações do usuário.  


### <a name="user-experience-impact"></a>Impacto da experiência do usuário

A seguir está uma visão geral da experiência de migração do correio de voz do usuário final.


|Enfrente  |Alteração na experiência do usuário|
|---------|---------|
|Notificação por email | Nenhuma alteração<br>Nenhum e-mail é enviado aos usuários notificando sobre a ativação/migração da conta de correio de voz. |
|Acesso às mensagens anteriores | Nenhuma alteração<br>Os usuários terão acesso às mensagens de correio de voz anteriores em todos os pontos de extremidade compatíveis. |
|Recebendo VM no Outlook, aplicativos SFB| Nenhuma alteração<br>Os usuários continuarão recebendo mensagens de correio de voz em todos os pontos de extremidade compatíveis. |
|Transcrição | Aumento<br>A transcrição CVM tem uma taxa de precisão muito mais alta e idiomas com suporte do que o ExchUMO. |
|Configuração do usuário | Nova experiência<br>Os usuários poderão alterar suas preferências a partir de um portal de configuração de usuário (USP). Os usuários podem acessar o USP a partir de um hiperlink no email de correio de voz ou o botão de configurações do usuário no cliente do SFB; https://aka.ms/vmsettings.   
 |Recursos| Para obter detalhes, consulte a comparação de conjuntos de recursos. |
|Regras do Outlook para mensagens VM | Nenhuma alteração<br>As regras criadas anteriormente serão aplicadas às mensagens CVM após a migração.
 |

#### <a name="user-management-and-provisioning-in-cvm"></a>Gerenciamento e provisionamento de usuários no CVM 

Os novos usuários do Skype for Business serão provisionados automaticamente para o correio de voz no serviço CVM quando forem criados. Não é necessário qualquer trabalho ou licença de administrador adicional para provisionar novos usuários para correio de voz. Consulte [Configurar o correio de voz na nuvem](/microsoftteams/set-up-phone-system-voicemail) para saber mais sobre o gerenciamento de políticas para usuários novos e existentes.

#### <a name="admin-auto-attendant-management-experience"></a>Experiência de gerenciamento do atendedor automático do administrador 

Consulte [configurar um atendedor automático na nuvem](/MicrosoftTeams/create-a-phone-system-auto-attendant.md) para saber mais sobre como configurar e gerenciar atendedores automáticos. 
