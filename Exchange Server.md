Obtener una lista de los buzones más grandes
Get-Mailbox -ResultSize Unlimited | Get-MailboxStatistics | Sort-Object TotalItemSize -Descending | Select-Object DisplayName,TotalItemSize -First 30
