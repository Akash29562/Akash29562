
if (eventData !== undefined && eventData.sourceProperty === "Temperature") {
    logger.info("Temperature changed, triggering sendMail service...");
    try {
        me.sendMail();
    } catch (err) {
        logger.error("Failed to call sendMail service: " + err.message);
    }
} else {
    logger.warn("Subscription triggered but not for Temperature property.");
}
