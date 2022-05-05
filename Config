import org.bukkit.Bukkit;
import org.bukkit.ChatColor;
import org.bukkit.configuration.file.FileConfiguration;
import org.bukkit.configuration.file.YamlConfiguration;
import org.bukkit.plugin.java.JavaPlugin;

import java.io.File;
import java.io.IOException;

public class Config {
    static FileConfiguration fileConfig;
    static File file;
    static String fileName;

    public static void setup(JavaPlugin plugin, String name) {
        // Configuration file
        file = new File(plugin.getDataFolder(), name);

        // If the file does not exist
        try {
            if (!file.exists()) file.createNewFile();
        } catch (IOException ignored) {}

        fileName = name;
        fileConfig = YamlConfiguration.loadConfiguration(file);
    }

    public static FileConfiguration getConfig() {
        return fileConfig;
    }

    public static void saveConfig() {
        try {
            fileConfig.save(file);
        } catch (IOException e) {
            Bukkit.getServer().getLogger().severe(String.format("%s[%s!%s] %sCould not save %s!", ChatColor.DARK_GRAY, ChatColor.RED, ChatColor.DARK_GRAY, ChatColor.GRAY, fileName));
        }
    }

    public static void reloadConfig() {
        fileConfig = YamlConfiguration.loadConfiguration(file);
    }
}
