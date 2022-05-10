Obtener una lista de los buzones más grandes

Get-Mailbox -ResultSize Unlimited | Get-MailboxStatistics | Sort-Object TotalItemSize -Descending | Select-Object DisplayName,TotalItemSize -First 30

Exportar a CSV una lista de los tamaños de los buzones

Get-Mailbox -ResultSize Unlimited | Get-MailboxStatistics | Sort-Object TotalItemSize -Descending | Select-Object DisplayName,TotalItemSize -First 100 | Export-CSV top100mailboxes.csv
